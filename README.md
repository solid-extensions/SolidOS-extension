# SolidOS Chrome Extension

A Chrome extension that automatically renders resources with `text/turtle` MIME type using the SolidOS data browser.

## Description

This Chrome extension intercepts web requests that return Turtle data (content type `text/turtle`) and redirects them to a built-in SolidOS data browser. This allows you to browse and interact with Linked Data on the Solid platform directly within your browser.

Key features:

- Automatic detection of Turtle data resources
- Integration with SolidOS data browser
- Authentication support for Solid identity providers
- Interactive navigation of linked data resources

## How It Works

When you visit a URL that returns content with the MIME type `text/turtle`, the extension:

1. Intercepts the response using Chrome's webRequest API
2. Redirects to the built-in data browser page
3. Loads the SolidOS data browser interface
4. Fetches and renders the Turtle data from the original URL

## Installation

### Development Installation

1. Clone this repository:

   ```
   git clone https://github.com/solid-extensions/SolidOS-extension.git
   cd SolidOS-extension
   ```

2. Open Chrome and navigate to `chrome://extensions/`

3. Enable "Developer mode" by toggling the switch in the top right corner

4. Click "Load unpacked" and select the directory where you cloned this repository

5. The extension should now be installed and active

## Testing

To test the extension:

1. Make sure the extension is installed as described above

2. Visit a URL that returns Turtle data with the `text/turtle` MIME type. Some examples:

   - https://solidcommunity.net/.well-known/solid
   - https://solidweb.org/.well-known/solid
   - https://solidproject.org/.well-known/solid

3. The extension should automatically redirect to the SolidOS data browser interface

4. You can log in with your Solid WebID to access private resources or stay as a public user for public resources

5. Use the address bar in the data browser to navigate to other Turtle resources

### Manual Testing

You can also manually enter URLs in the data browser's address bar and click "Go" to navigate to any Turtle resource, even if it wasn't initially detected by the extension.

## Development

The extension consists of the following key components:

- `background.js`: Handles the webRequest interception and redirection logic
- `databrowser.html`: The main HTML page for the SolidOS data browser interface
- `databrowser.js`: JavaScript code that initializes and configures the SolidOS data browser
- `mashlib.min.js` and `mashlib.min.css`: The SolidOS library that powers the data browser

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Related Projects

- [Solid Project](https://solidproject.org/)
- [SolidOS](https://github.com/SolidOS)
