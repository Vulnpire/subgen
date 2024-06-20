# Subgen

reads a list of domains and a wordlist, then generates all possible subdomains by prepending each word from the wordlist to each domain. This tool is ideal for quickly generating a large number of subdomains for further DNS resolution.

## Installation

To use Subgen, ensure you have Python 3 installed. Follow these steps to get started:

`git clone https://github.com/Vulnpire/subgen && cd subgen && chmod +x subgen && mv subgen /usr/bin/`

## Usage

Subgen requires two input files: one containing domains and another containing words for subdomain generation.

Arguments

    -f, --file: Path to the file containing the list of domains.
    -w, --wordlist: Path to the file containing the wordlist for subdomains.

Example

Suppose you have the following files:

```
nl domains.txt

1 example.com
2 test.com
```

```
nl wordlist.txt

1 dev
2 www
3 mail
```

## Running the command

`subgen -f domains.txt -w wordlist.txt`

Will produce the following output:

```
dev.example.com
www.example.com
mail.example.com
dev.test.com
www.test.com
mail.test.com
```

Efficiency and Use Cases

SubdomainGenerator is designed to quickly generate a comprehensive list of subdomains. You can further integrate this tool with DNS resolution tools to validate the existence of these subdomains. For example, you can use a tool like `dnsx` to filter active subdomains from the generated list.
