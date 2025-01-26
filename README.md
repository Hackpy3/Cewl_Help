# Cewl_Help
CeWL (Custom Word List Generator) is a Ruby-based tool used in penetration testing to generate custom wordlists. It can crawl a target website and extract words that might be useful for password cracking or other purposes. Here's how to install and use CeWL in Kali Linux:

### 1. **Check if CeWL is already installed**
Kali Linux often includes CeWL by default. Check if it's installed by running:
```bash
cewl --help
```
If you see help output, CeWL is already installed.

### 2. **Install CeWL (if not installed)**
If CeWL is not installed, you can install it using the following steps:

#### a. Update the package list
```bash
sudo apt update
```

#### b. Install CeWL
```bash
sudo apt install cewl
```

#### c. Verify the installation
Check the version of CeWL to ensure it’s installed:
```bash
cewl --version
```

### 3. **Using CeWL**
Basic usage involves running the `cewl` command with the target URL:
```bash
cewl https://example.com
```

#### Common Options:
- **`-d`**: Specify the depth to crawl (default is 2).
  ```bash
  cewl -d 3 https://example.com
  ```
- **`-m`**: Minimum word length to include.
  ```bash
  cewl -m 5 https://example.com
  ```
- **`-o`**: Output results to a file.
  ```bash
  cewl -o wordlist.txt https://example.com
  ```
- **`-e`**: Include email addresses.
  ```bash
  cewl -e https://example.com
  ```

### 4. **Troubleshooting**
If CeWL doesn’t work or gives errors:
- Ensure Ruby is installed and updated:
  ```bash
  sudo apt install ruby
  ```
- Check if dependencies are missing, and install them:
  ```bash
  sudo apt install ruby-dev build-essential
  ```
- Reinstall CeWL if necessary:
  ```bash
  sudo apt remove cewl && sudo apt install cewl
  ```

Now you're ready to use CeWL for creating custom wordlists! Let me know if you need help with a specific use case.
