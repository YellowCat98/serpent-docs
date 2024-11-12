# Initializing a script
- In order to create a script, create a folder, this can be anywhere!
- inside this folder, there'll be two files.
- `script.json`: This is a json file which includes mod metadata, this is the required syntax for it:
```json
// (this is only in jsonc for explaining what each key does, note that your script.json must not have comments! (i think it should work fine though))
{
	"serpent": "1.0.0", // This is the version of Serpent that the script is made for.
	"name": "Simple Script", // This is the name for the script
	"id": "simplescript_yellowcat98", // This is the ID of the script to avoid collision between other scripts!
	"developer": "YellowCat98" // The developer of the script!
}
```
- `mod_id.py`: This is the main script! note that it is required for it to have the same name as the ID otherwise it won't execute! (check the Script syntax section )

- Now that it's been set up, you're ready to start coding!