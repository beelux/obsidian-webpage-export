# Webpage HTML Export

Exports an obsidian document, folder, or vault as an HTML document / webpage / website, **(correctly!)** including all styling and formatting.

![image](https://user-images.githubusercontent.com/39423700/201875810-6d24c2b9-2e63-4d9b-a9d4-61840df659ac.png)

## Canvas Support
Canvas support is currently very preliminary. Your canvas documents will export, but large documents included wll not render fully, and documents larger than one screen will be cut off or documents will become invisible. Small simple canvas documents should work fine.

## Features:
- Export files, folders, or the whole vault as html. [Explained in: General](#general)
- Support for Kanban, and Canvas documents (and possibly other plugins that haven't been tested)!
- Color theme toggle can be embedded anywhere on the page. [Explained in: Theme Toggle](#theme-toggle)
- Supports images, with automatic base64 inlining, or by exporting the images seperately. [Explained in: Non-Inlined Files](#non-inlined-files)
- Supports inline CSS, or exporting seperately. [Explained in: Non-Inlined Files](#non-inlined-files)
- Supports inline JS, or exporting JS seperately. [Explained in: Non-Inlined Files](#non-inlined-files)
- Supports snippets, and custom themes (both light and dark).
- Interactively collapse and unfold headers like in obsidian
- Export documents with onclick attributes working. [Explained in: On Click Atrributes](#on-click-attributes)

## FAQ

#### General
<details><summary>General Instructions</summary>
<p>

- From any of the file / folder context menus select `Export As HTML`. Or to export the whole vault use the ribbon icon.

- Change options as desired. Special options are explained below.

- Click Export, and select a location for the file

</p>
</details>

#### Theme Toggle
<details><summary>How do I include a light and dark mode toggle?</summary>
<p>

- Any `theme-toggle` code block will be replaced with a toggle for changing the theme. That means:
> \`theme-toggle\`
> 
> \`\`\`theme-toggle\`\`\`

or

> \`\`\`theme-toggle
> 
> \`\`\`

- This toggle does not work inside of obsidian, however once exported it will (this may change in the future)
- If you do not include \`theme-toggle\` in a document and the `Add Dark Mode Toggle` setting is on then a toggle will be fixed to every page in the top left corner.


</p>
</details>


#### Non-Inlined Files:
<details><summary>How do I export my images, js, or css as seperate files?</summary>
<p>

- If exporting CSS or JS seperately those files will be exported into the same folder as the .HTML
- Images will be placed relative to the .HTML file the same as they were in obsidian.
- The exception to this is if the images were heigher in the heirarchy than the .HTML file, in which case the images are placed in a `/image` directory.
- All references and links to images or files are updated automatically.
- When exporting a folder or vault with non-inlined files every file will have its own copy of each file. This is something that works for now but is far from optimal. Hopefully this will be updated in the future.

</p>
</details>

#### Inluding Plugin CSS
<details><summary>How do I include css added by other plugins?</summary>
<p>

- If you want to include css from a plugin (like Kanban for example) in the export
- Start exporting your file and stop on the settings modal
- Locate the `Include Plugin CSS` setting
- Ender a list of plugin `IDs` each on a seperate line (for example kanban's ID is `obsidian-kanban`)
- This may get more user friendly in the future, but for now it's the fastest implementation.


</p>
</details>

#### On Click Attributes

<details><summary>How do I make buttons or other elements with an 'on-click' attribute work after export?</summary>
<p>

This is a somewhat niche feature; however, if you want to use the `onlick` attribute in your exported HTML without editing it afterwards you can use simple feature in this plugin to do that:
1. Replace the `onclick` attribute in your source with `data-onclick`.
2. Export the file, and this attribute will be replaced with onclick in the exported html.

Note: This does not enable `onclick` inside of obsidian itself. 

</p>
</details>

## Screenshots:

<details><summary>Click to view more screenshots</summary>
<p>
Dark mode document with the outline enabled

![image](https://user-images.githubusercontent.com/39423700/208754928-82eb3a4a-6018-4be9-a098-abc2800d6d32.png)

Light mode document with the outline enabled

![image](https://user-images.githubusercontent.com/39423700/208754972-f9bc22be-8f0c-48ff-aab8-2e25e7052790.png)

Canvas export

![image](https://user-images.githubusercontent.com/39423700/208755062-62311347-a15f-4ae5-b798-8a5719934988.png)

Kanban export

![image](https://user-images.githubusercontent.com/39423700/208755364-919894b3-2107-4a29-bd9b-06f75521c25a.png)
</p>
	
Export options
	
![image](https://user-images.githubusercontent.com/39423700/208756140-37c212b5-0647-45b8-98ed-922765095a4e.png)

</details>


## Contributing
- Please let me know before starting work on a feature!
- I am open to any PRs as long as they align with my vision for the plugin. So if you are going to work on a feature that isn't already an issue, then please submit an issue instead.
- When changing files in the `assets` folder, you must set `autoDownloadExtras` to false inside of html-gen.ts, or it will redownload the files and overwrite your changes. Once you've finished only commit your changes to the assets folder (not html-gen.ts). Unfortunately, it will keep overwriting your results every time the plugin is reloaded, until those changes are part of the main branch on github.

## Credits
Thanks to https://github.com/darlal/obsidian-switcher-plus for reference for opening specific files in a new tab.

## Coffee

This plugin takes a lot of work to maintain and continue adding features. If you want to fund the continued development of this plugin you can do so here:

<a href="https://www.buymeacoffee.com/nathangeorge"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a coffee&emoji=&slug=nathangeorge&button_colour=6a8695&font_colour=ffffff&font_family=Poppins&outline_colour=000000&coffee_colour=FFDD00"></a>
