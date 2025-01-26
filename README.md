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
Here are additional examples of using **CeWL** with various options to suit different use cases:

---

### 1. **Basic Crawl of a Website**
Crawl a website and display the words in the terminal:
```bash
cewl https://example.com
```

---

### 2. **Set the Depth of Crawling**
Control how many levels deep CeWL should go when following links:
```bash
cewl -d 3 https://example.com
```
This will crawl up to 3 levels deep.

---

### 3. **Limit the Minimum Word Length**
Filter out short words by specifying a minimum word length:
```bash
cewl -m 6 https://example.com
```
This ensures only words with 6 or more characters are included.

---

### 4. **Save Output to a File**
Save the generated wordlist to a file:
```bash
cewl -o wordlist.txt https://example.com
```
The wordlist will be saved in `wordlist.txt`.

---

### 5. **Include Email Addresses**
Scrape email addresses from the target website:
```bash
cewl -e https://example.com
```

---

### 6. **Use a Custom User-Agent**
Specify a custom user-agent to avoid detection or blocking:
```bash
cewl -u "Mozilla/5.0 (Windows NT 10.0; Win64; x64)" https://example.com
```

---

### 7. **Generate a Wordlist with Metadata**
Extract metadata (e.g., author names, document titles) from documents like PDFs:
```bash
cewl --meta https://example.com
```
This can help find sensitive data hidden in file metadata.

---

### 8. **Authenticate with HTTP Basic Authentication**
If the website requires a username and password, include them with the `-u` and `-p` options:
```bash
cewl -u username -p password https://example.com
```

---

### 9. **Use Proxy for Crawling**
Route requests through a proxy:
```bash
cewl --proxy_host 127.0.0.1 --proxy_port 8080 https://example.com
```
This is useful for anonymity or routing through tools like Burp Suite.

---

### 10. **Limit the Number of Words**
Specify the maximum number of words to retrieve:
```bash
cewl -w 100 https://example.com
```
This limits the wordlist to 100 words.

---

### 11. **Combine Options**
Combine multiple options to fine-tune your crawl. For example:
- Crawl 2 levels deep, save to a file, extract metadata, and filter by minimum word length:
```bash
cewl -d 2 -m 5 --meta -o wordlist.txt https://example.com
```

---

### 12. **Follow Non-Standard Links**
If the site uses unconventional extensions for pages, use the `--auth_type` and `--auth_arg` options:
```bash
cewl --auth_type "digest" --auth_arg "username:password" https://example.com
```

---

### 13. **Debugging and Verbose Mode**
Use verbose mode to see more details about what CeWL is doing:
```bash
cewl -v https://example.com
```

---

### 14. **Ignore Certain Content**
Exclude specific file types (e.g., images or scripts):
```bash
cewl --no-words https://example.com
```

---

### 15. **Combine CeWL with Other Tools**
Combine CeWL with tools like **John the Ripper** or **Hashcat** for password cracking. For example:
1. Generate the wordlist:
   ```bash
   cewl -m 5 -o cewl-wordlist.txt https://example.com
   ```
2. Use the wordlist in John the Ripper:
   ```bash
   john --wordlist=cewl-wordlist.txt hashes.txt
   ```

Let me know if you'd like help with more advanced use cases!
Now you're ready to use CeWL for creating custom wordlists! Let me know if you need help with a specific use case.
