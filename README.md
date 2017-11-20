# Sitecore snippets
This project includes a collection of code snippets for some of the most common Sitecore tasks like retrieving the home item, datsource, rendering item fields, etc.
The snippets are packaged inside a *.vsix Visual Studio Package for ease of installation.

## Installation
Download and execute the [vsix file](/output/Sitecore.Snippets.vsix).

If you don't want to install all the snippets, you can also import individual ones using the *Code Snippets Manager* in Visual Studio.

## Compilation
Just build the project. The vsix file is in the bin folder as usual.

## Contribute
Modify or add new snippets. For the snippet files to be included in the VSIX file you need to ensure the following properties are set:
Build Action: Content
Copy to output directory: Copy always
Include in VSIX: true

You can simply execute the project (Ctrl+F5) to open an experimental copy of Visual Studio (another copy but with different extensions/settings) with the package installed to try the snippets.

## Known issues
You can't insert HTML snippets directly using the shorcut and pressing TAB twice (as you do with C# snippets). However you can press Ctrl+K, X and use the Contextual menu to navivgate the available snippets. There are also issues tabbing, or pressing ENTER whilst editing a placeholder value in an HTML snippet.

The Kind attribute in the CodeSnippet element is ignored. This allows to incorrectly add snippets that may not be syntactically correct in the current context (like a property definition inside a method body).

## Available snippets
You can use the Snippet Manager in Visual Studio to see the available snippets. All snippets start with the prefix "sc". Press TAB twice to use the snippet. A few of the snippets can also be used as surround snippets (Ctrl+K,S).

### C# Snippets
* scDatasource - reference to the Datsource (defaults to context item) in code, typically in a controller rendering.
* scEditContext - using clause with an EditContext for modifying values in an item. Can be used as a surround snippet.
* scField - obtain a reference to a field object of an item. By default it uses a Field object but it is a placeholder so you can modify the class to use a more specific field type (ImageField, ReferenceField, etc.)
* scHome - create a new variable with a reference to the home item, obtained from the Context Site.
* scMultilistIterator - retrieve a MultilistField and create a foreach loop to iterate over its elements
* scParameters - get a reference to the rendering parameters collection and retrieve a particular key value.
* scPropRender - useful when creating a custom model. Create an HtmlString property which renders a particular field from the datasource/context item.
* scRender - invoke the FieldRenderer.Render method to output a field in code
* scRenderHtmlString - add a new HtmlString object with a FieldRenderer.Render method to output a field in code
* scSearh - a big snippet showing how to do a simple search using the ContentSearch API.
* scSecurityDisabler - add a using with a security Disabler. Can be used as a surround snippet.
* scUrl - add a reference to the LinkManager.GetItemUrl to obtain a string with the href.
* scUserSwitcher - add a user switcher impersonating a known user name. Can be used as a surround snippet.

### HTML Snippets
* scHtmlField - add an HTML helper with Field extension method. There is a alternate version with some common image manipulation parameters.