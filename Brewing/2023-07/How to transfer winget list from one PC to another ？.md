Here are the steps I would recommend for transferring winget list from one PC to another:

1. On the source PC (the PC with the existing winget list), open an administrative command prompt (e.g. by right clicking Command Prompt and selecting "Run as administrator"). 

2. Run the command "winget export --output winget.manifest" to export the list to a manifest file. This will create a winget.manifest file that contains the list of all installed apps.

3. Transfer the winget.manifest file to the target PC (the PC you want to import the list to), e.g. by emailing it or copying it to a USB drive.

4. On the target PC, open an administrative command prompt.

5. Run the command "winget import --manifest winget.manifest" to import the list from the manifest file. This will install all the apps listed in the manifest file. 

6. Winget will check for any conflicts and prompt you to resolve them (e.g. if an app with the same name is already installed). Follow the prompts to complete the import.

Let me know if you have any trouble following these steps or have any other questions! I'll do my best to help guide you through the process. The important part is exporting the manifest file from the source PC and then importing it on the target PC.