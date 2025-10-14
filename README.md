🧰 Setup
Clone the repository:
bash
git clone https://github.com/yourusername/Ghost_Spotter.git
cd Ghost_Spotter

Create a virtual environment (optional but recommended):
bash
python3 -m venv venv
source venv/bin/activate

Install dependencies:
bash
pip install tqdm

Run the tool:
bash
python3 Ghost_Spotter.py <hash> ...

🕵️‍♂️ Ghost_Spotter

🔧 Features
- Supports 10 hash algorithms via Python’s `hashlib`
- Wordlist-based cracking with progress tracking
- Brute-force cracking with customizable charset and length bounds
- Threaded execution for speed (`ThreadPoolExecutor`)
- CLI interface via `argparse`
- Real-time progress bars via `tqdm`

🔢 Supported Hash Types
| Hash Type   | Length (Hex) | Example Use Case        |
|-------------|--------------|--------------------------|
| md5         | 32           | Legacy systems, quick checks |
| sha1        | 40           | Older web apps, Git commits |
| sha224      | 56           | Niche cryptographic use |
| sha256      | 64           | Modern web apps, JWT |
| sha384      | 96           | High-security tokens |
| sha512      | 128          | Banking, secure storage |
| sha3_224    | 56           | SHA-3 family |
| sha3_256    | 64           | SHA-3 family |
| sha3_384    | 96           | SHA-3 family |
| sha3_512    | 128          | SHA-3 family |

🚀 Usage Examples
Wordlist-based cracking
bash:
python3 Ghost_Spotter.py <hash> -w /path/to/wordlist.txt --hash_type sha256

Actual example on how to bash it in a OS terminal below. I cracked a password that I made with a SHA generator to demonstrate:

$ python3 Ghost_Spotter.py 3a38358d2d44714bc66023ccbe203acf41fda6af7320c8af06556c7f7888f6cb8d9a3c934fb47a93625ebb0cb03fa4466a437ae880975dc13106c48566ea14aa --hash_type sha512 --min_length 4 --max_length 6 -c 1234567890

Results:

└─$ python3 Ghost_Spotter.py 3a38358d2d44714bc66023ccbe203acf41fda6af7320c8af06556c7f7888f6cb8d9a3c934fb47a93625ebb0cb03fa4466a437ae880975dc13106c48566ea14aa --hash_type sha512 --min_length 4 --max_length 6 -c 1234567890
[*] Cracking hash 3a38358d2d44714bc66023ccbe203acf41fda6af7320c8af06556c7f7888f6cb8d9a3c934fb47a93625ebb0cb03fa4466a437ae880975dc13106c48566ea14aa using sha512 with generated passwords of lengths from 4 to 6. Total combinations: 1110000.
Generating and cracking hash:   0%|▎                                                                                                                  | 3367/1110000 [00:00<00:35, 31492.31it/s]
[+] Password found: 4477

Note:
When bashing use --min_length & --max_length to suit your needs, 4 & 6 were just for this demonstration.

📜 License
This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0).

You are free to:

Share — copy and redistribute the material in any medium or format

Adapt — remix, transform, and build upon the material

Under the following terms:

Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made.

NonCommercial — You may not use the material for commercial purposes.

https://creativecommons.org/licenses/by-nc/4.0/

