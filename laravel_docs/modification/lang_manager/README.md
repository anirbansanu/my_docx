# `Manager` Class Documentation

The `Manager` class is part of the `App\Overrides\Langman` namespace and is designed to manage language files within a Laravel application. It provides methods for reading, writing, and manipulating language files, including support for JSON and PHP file formats. Below is the documentation for this class, explaining its properties and methods.

## Properties

### `private $disk`

- Type: `Filesystem`
- Description: The Filesystem instance used for interacting with files.

### `private $path`

- Type: `string`
- Description: The path to the directory where language files are stored.

### `private $syncPaths`

- Type: `array`
- Description: An array of directories to search for localized strings to sync.

### `private $extension`

- Type: `string`
- Description: The extension used for language files (e.g., 'php' or 'json').

### `private $exclude_extensions`

- Type: `array`
- Description: An array of file extensions to be excluded when searching for language files.

## Methods

### `__construct(Filesystem $disk, $path, array $syncPaths)`

- Description: Constructor method to initialize the Manager instance.
- Parameters:
  - `$disk` (Type: `Filesystem`) - The Filesystem instance.
  - `$path` (Type: `string`) - The path to the language files directory.
  - `$syncPaths` (Type: `array`) - An array of directories to search for localized strings to sync.

### `setExtension($extension)`

- Description: Set the extension for language files.
- Parameters:
  - `$extension` (Type: `string`) - The new file extension to set.

### `setExcludeExtensions($exclude_extensions)`

- Description: Set the list of file extensions to be excluded when searching for language files.
- Parameters:
  - `$exclude_extensions` (Type: `array`) - An array of file extensions to exclude.

### `getJsonFilesContent($filesByFile, $lang)`

- Description: Retrieve the contents of JSON language files for a specific language.
- Parameters:
  - `$filesByFile` (Type: `array`) - An array of language files grouped by file name.
  - `$lang` (Type: `string`) - The target language.
- Returns:
  - Type: `array` - An array of language file contents for the specified language.

### `files()`

- Description: Get a list of language files grouped by file name.
- Returns:
  - Type: `array` - An array of language files grouped by file name.

### `genarateLang($lang_name)`

- Description: Generate a new language folder by copying an existing one.
- Parameters:
  - `$lang_name` (Type: `string`) - The name of the new language folder.
- Returns:
  - Type: `int` - `1` if successful, `0` if failed.

### `neglectVendorFiles($filesByFile)`

- Description: Exclude vendor-specific language files.
- Parameters:
  - `$filesByFile` (Type: `Collection`) - A collection of language files.
- Returns:
  - Type: `array` - An array of language files with vendor files neglected.

### `filterByIncludedFileNames($filesByFile, $includedFileNames)`

- Description: Include only specified language files by name.
- Parameters:
  - `$filesByFile` (Type: `array`) - An array of language files grouped by file name.
  - `$includedFileNames` (Type: `array`) - An array of file names to include.
- Returns:
  - Type: `array` - An array of included language files.

### `filterByExcludedFileNames($filesByFile, $excludedFileNames)`

- Description: Exclude specified language files by name.
- Parameters:
  - `$filesByFile` (Type: `array`) - An array of language files grouped by file name.
  - `$excludedFileNames` (Type: `array`) - An array of file names to exclude.
- Returns:
  - Type: `array` - An array of excluded language files.

### `getSupportedLanguages($filesByFile)`

- Description: Get all supported languages based on the provided language files.
- Parameters:
  - `$filesByFile` (Type: `array`) - An array of language files grouped by file name.
- Returns:
  - Type: `array` - An array of supported language codes.

### `languages()`

- Description: Get a list of supported language codes.
- Returns:
  - Type: `array` - An array of supported language codes.

### `createFile($fileName)`

- Description: Create a language file for all supported languages if it does not exist already.
- Parameters:
  - `$fileName` (Type: `string`) - The name of the language file to create.

### `fillKeys($fileName, array $keys)`

- Description: Fill translation lines for given keys in different languages.
- Parameters:
  - `$fileName` (Type: `string`) - The name of the language file.
  - `$keys` (Type: `array`) - An array of keys and their translations in different languages.

### `removeKey($fileName, $key)`

- Description: Remove a key from all language files.
- Parameters:
  - `$fileName` (Type: `string`) - The name of the language file.
  - `$key` (Type: `string`) - The key to remove from all language files.

### `writeFile($filePath, array $translations)`

- Description: Write a language file from an array of translations.
- Parameters:
  - `$filePath` (Type: `string`) - The path to the language file.
  - `$translations` (Type: `array`) - An array of translations to write to the file.

### `stringJsonLineMaker($array, $prepend = '')`

- Description: Generate the lines of the inner array of a JSON language file.
- Parameters:
  - `$array` (Type: `array`) - The array to generate lines from.
  - `$prepend` (Type: `string`) - The prefix to prepend to each line.
- Returns:
  - Type: `string` - The generated lines as a string.

### `stringLineMaker($array, $prepend = '')`

- Description: Generate the lines of the inner array of a PHP language file.
- Parameters:
  - `$array` (Type: `array`) - The array to generate lines from.
  - `$prepend` (Type: `string`) - The prefix to prepend to each line.
- Returns:
  - Type: `string` - The generated lines as a string.

### `getFileContent($filePath, $createIfNotExists = false)`

- Description: Get the content of a language file.
- Parameters:
  - `$filePath` (Type: `string`) - The path to the language file.
  - `$createIfNotExists` (Type: `bool`) - Whether to create the file if it does not exist.
- Returns:
  - Type: `array` - An array representing the content of the language file.

### `collectFromFiles()`

- Description: Collect all translation keys from view files.
- Returns:
  - Type: `array`

 - An array of translation keys found in view files.

### `getAllViewFilesWithTranslations()`

- Description: Get translation lines found per view file.
- Returns:
  - Type: `array` - An array containing view file names as keys and arrays of translation lines as values.

### `setPathToVendorPackage($packageName)`

- Description: Set the path to language files within a vendor package.
- Parameters:
  - `$packageName` (Type: `string`) - The name of the vendor package.

### `getKeysExistingInALanguageButNotTheOther($values)`

- Description: Extract keys that exist in one language but not in another.
- Parameters:
  - `$values` (Type: `array`) - An array of keys in the format 'file.language.key'.
- Returns:
  - Type: `array` - An array of keys that exist in one language but not in another.

This documentation provides an overview of the `Manager` class and its functionality. You can use this class to manage language files efficiently within a Laravel application, including creating, updating, and synchronizing translations.