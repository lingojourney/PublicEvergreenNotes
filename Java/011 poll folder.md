If you're looking for a simpler solution without Spring, you can use plain Java to poll a directory for changes. Here's an example using `java.nio.file` package which provides a `WatchService` API to monitor directory events:

```java
import java.nio.file.*;
import static java.nio.file.StandardWatchEventKinds.*;
import java.io.IOException;

public class DirectoryPoller {
    private final Path dir;
    private final WatchService watcher;

    public DirectoryPoller(Path dir) throws IOException {
        this.dir = dir;
        this.watcher = FileSystems.getDefault().newWatchService();
        this.dir.register(watcher, ENTRY_CREATE, ENTRY_DELETE, ENTRY_MODIFY);
    }

    public void pollDirectory() {
        for (;;) {
            WatchKey key;
            try {
                key = watcher.take();
            } catch (InterruptedException x) {
                return;
            }

            for (WatchEvent<?> event : key.pollEvents()) {
                WatchEvent.Kind<?> kind = event.kind();

                if (kind == OVERFLOW) {
                    continue;
                }

                WatchEvent<Path> ev = (WatchEvent<Path>)event;
                Path filename = ev.context();

                // Here you can define the logic to handle the new file
                // For example, upload it to HCP

                System.out.println(kind.name() + ": " + filename);
            }

            boolean valid = key.reset();
            if (!valid) {
                break;
            }
        }
    }

    public static void main(String[] args) throws IOException {
        Path dir = Paths.get("/path/to/directory");
        new DirectoryPoller(dir).pollDirectory();
    }
}
```

Replace `"/path/to/directory"` with the path to the directory you want to monitor. This code will print out the event type and the file name whenever a file is created, deleted, or modified in the specified directory.

You can add your logic to handle the file, such as uploading it to HCP, within the `pollDirectory` method where the comment is placed.

This approach uses the `WatchService` API, which is part of the Java NIO package and provides a more efficient way to monitor directories compared to polling at regular intervals¹.

Source: Conversation with Bing, 02/05/2024
(1) Java: how to poll a small file over and over to see if it changed .... https://stackoverflow.com/questions/63096565/java-how-to-poll-a-small-file-over-and-over-to-see-if-it-changed-watching-can.
(2) polling a file in java, get the latest written file content to a string. https://stackoverflow.com/questions/37322561/polling-a-file-in-java-get-the-latest-written-file-content-to-a-string.
(3) java - How to poll directory to check whether new file is added .... https://stackoverflow.com/questions/7344331/how-to-poll-directory-to-check-whether-new-file-is-added.
(4) undefined. https://blogs.oracle.com/thejavatutorials/entry/watching_a_directory_for_changes.
(5) github.com. https://github.com/windname/java-core/tree/ac5777d51d25d7dec6c6c4658e9bf9b3f82937ce/src%2Fmain%2Fjava%2Fcom%2Fvg%2Fcertif%2Fnio2%2FFileSysUpdate.java.
(6) github.com. https://github.com/bharatl/zeppelin/tree/651286bd06e1fce332efff420013548855b943bc/zeppelin-interpreter%2Fsrc%2Fmain%2Fjava%2Forg%2Fapache%2Fzeppelin%2Finterpreter%2FInterpreterOutputChangeWatcher.java.
(7) github.com. https://github.com/HammadShuaib/GPUCFed/tree/fcf1f17e9f4b2f4a45f4b13c2bd48c6a4f02131e/costfed%2Fsrc%2Fmain%2Fjava%2Forg%2Faksw%2Fsimba%2Fquetsal%2Fconfiguration%2FCostFedSummaryProvider.java.