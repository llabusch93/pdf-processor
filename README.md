# PDF Processor

PDF Processor is a Python CLI application that processes PDF documents and renames them based on AI-generated descriptions. This tool is designed to help organize and manage collections of PDF documents by extracting meaningful information and creating standardized filenames.

## Features

- Process single PDF files or entire directories recursively
- Generate meaningful filenames using OpenAI's GPT models
- Multiprocessing support for faster batch processing
- Customizable number of worker processes
- Language selection for filename generation

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/llabusch93/pdf-processor.git
   cd pdf-processor
   ```

2. Create a virtual environment and activate it:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Set up your OpenAI API key as an environment variable:
   ```
   export OPENAI_API_KEY=your_api_key_here
   ```

## Usage

To process a single PDF file:

```
pdf-processor /path/to/your/file.pdf
```

To process all PDF files in a directory recursively:

```
pdf-processor /path/to/your/directory
```

To specify the number of worker processes:

```
pdf-processor /path/to/your/directory --workers 5
```

To specify the language for filename generation:

```
pdf-processor /path/to/your/file.pdf --language english
```

## How it works

1. The program checks if the input is a single file or a directory.
2. For each PDF file:
   a. The text is extracted from the PDF.
   b. The extracted text is sent to OpenAI's GPT model to generate a meaningful filename.
   c. The file is renamed using the generated filename.
3. If processing a directory, multiple files are processed concurrently using Python's `multiprocessing` module.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

Laurence Labusch (laurence.labusch@gmail.com)

