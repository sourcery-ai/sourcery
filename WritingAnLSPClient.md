# Introduction
Sourcery is a standards compliant Language Server as defined by the [LSP spec](https://microsoft.github.io/language-server-protocol/specifications/specification-current/).

To create a fully working client (code editor extension) you only need to:
1. Download and unpack the binaries.
2. Start up the relevant binary for the current OS.
3. Initialize the Sourcery Language Server with Sourcery specific initialization options.
4. Follow the standard LSP spec (almost all editors have libraries for doing this).
5. Tell us about it so we can spread the word!

## Binaries
The latest binaries are available on the [sourcery-ai/sourcery releases page](https://github.com/sourcery-ai/sourcery/releases/latest). Once downloaded they must be unpacked before they can be run.

The unpacked binaries can be checked on your system by running `path_to_binary/sourcery --verify` which will print out a message similar to:
```
sourcery, version 0.7.11

Verifying server availability https://api.sourcery.ai/health - success
Verifying refactoring functionality - success
```

## Startup and Initialisation
The client communicates with The Sourcery Language Server through standard input and output. To run the Sourcery Language Server execute `path_to_binary/sourcery lsp`.

The Sourcery Server is initialised with the standard [LSP initialize request](https://microsoft.github.io/language-server-protocol/specifications/specification-current/#initialize). It requires the `initializationOptions` param to be populated as shown below and will respond with the list of ServerCapabilities that it supports.

```ts
interface SourceryInitializationOptions: {
    /**
     * The Sourcery token for authenticating the user.
     * This is retrieved from the Sourcery website and must be
     * provided by each user. The extension must provide a
     * configuration option for the user to provide this value.
     */
    token: string;

    /**
     * The extension's name and version as defined by the extension.
     * e.g. sourcery-ai/vscode 0.7.6
     */
    extension_version: string;

    /**
     * The editor's name and version as defined by the editor.
     * e.g. vscode 1.44.0
     */
    editor_version: string;
}
```

Once the Sourcery Language Server is initialized it will act in a fully LSP compliant manner providing refactoring suggestions and hover functionality.

## Let us know!
if you implement a new client for a editor we'd love to hear about it and are happy to help if you need any assistance. Just drop us a line at hello@sourcery.ai
