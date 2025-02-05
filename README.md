# fdup - Fast Duplicate File Finder

A command-line tool that efficiently finds and manages duplicate files in your filesystem. Built with performance in mind, fdup uses smart size-based pre-filtering and SHA-256 hashing to accurately identify duplicates while minimizing unnecessary file reads.

### Requires Python3 to be installed

## Features

- 🚀 Fast scanning with size-based pre-filtering
- 🔒 Secure file comparison using SHA-256 hashing
- 📊 Real-time progress bars for all operations
- 🤖 Supports both interactive and automated deletion modes
- 🎯 Customizable directory ignore patterns
- ⚡ Memory-efficient chunk-based file processing

## Installation

```bash
# Clone the repository
git clone https://github.com/benjamincoad/fdup.git

# Make the script executable
chmod +x fdup
```

## Usage

```bash
# Basic interactive mode
./fdup /path/to/directory

# Auto-delete duplicates (keeps first file in each group)
./fdup -a /path/to/directory

# Delete ALL files in duplicate groups (use with caution!)
./fdup -d /path/to/directory

# Ignore specific directories
./fdup --ignore .git node_modules /path/to/directory
```

### Command Line Options

- `-a, --auto-delete`: Automatically delete duplicates while keeping the first file
- `-d, --delete-all`: Delete all files in duplicate groups (use with caution!)
- `-i, --ignore`: Specify patterns to ignore (default: .git, __pycache__, node_modules, .venv)
- `directory`: Directory to scan (default: current directory)

## How It Works

1. **Initial Scan**: Recursively collects all files in the specified directory
2. **Size Grouping**: Groups files by size to identify potential duplicates
3. **Hash Verification**: Uses SHA-256 hashing to confirm true duplicates
4. **Deletion Options**:
   - Interactive: Choose which files to delete with a user-friendly interface
   - Automatic: Delete duplicates while keeping the first file
   - Full Group: Option to delete all files in duplicate groups

## Safety Features

- Progress tracking for all operations
- 3-second warning before automatic deletion
- Ctrl+C cancel option during auto-delete
- Size information displayed before deletion
- Cannot use both auto-delete modes simultaneously

## License

MIT License - feel free to use and modify as needed!

## Contributing

Contributions are welcome! Feel free to submit issues and pull requests.
