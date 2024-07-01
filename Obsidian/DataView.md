```dataview
LIST 
WHERE contains(file.content, "Benson")
```

[Dataview in Obsidian: A Beginner's Guide - Obsidian Rocks](https://obsidian.rocks/dataview-in-obsidian-a-beginners-guide/#Limiting-to-folders)



%%
````md
```dataview
list without id item.text
from "countries" and "states"
flatten file.lists as item
where contains(item.tags, "#check/gayan")
```
````
%%

