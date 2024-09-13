# Welcome to the GIIS Tech Club DNS Hub! 🚀

Ready to dive into the world of DNS and help shape the infrastructure of giistech.club? Whether you're a tech enthusiast or a curious explorer, this is your chance to make a tangible impact with just a few clicks. By tweaking a YAML file and opening a pull request, you'll set the wheels in motion, automatically updating our DNS records with Cloudflare. Let's get started!

## Why DNS?

DNS (Domain Name System) is like the internet's phonebook, translating human-readable domain names into IP addresses. It's crucial for:

- **Website Hosting**: Directing domain names to server IPs so visitors can reach your website.
- **Email Routing**: Ensuring emails reach the right destination through MX records.
- **Service Discovery**: Helping applications locate services through SRV records.
- **Security**: Using TXT records for configurations like SPF to protect email authenticity.

## How to Contribute DNS Records

### Step 1: Fork the Repository

- Click the "Fork" button at the top right of this repository page.

![image](https://github.com/user-attachments/assets/c9af532f-0ba0-4fa1-8423-c813e6509291)

### Step 2: Edit Files via GitHub

1. **Go to Your Fork**: Navigate to your forked repository.

2. **Open the File**: Find and open `giistech.club.yaml`.

3. **Edit the YAML File**: Click the pencil icon to edit.

![image](https://github.com/user-attachments/assets/8b1ebecf-30ee-4ce7-ab5c-1f4f489729b8)

- Add or modify records using this structure:

  ```yaml
  subdomain:
    ttl: <TTL value in seconds>
    type: <Record type (A, CNAME, MX, etc.)>
    value: <Record value>
    octodns:
      cloudflare:
        proxied: <true/false>
        auto_ttl: <true/false>
  ```

  **Example - A Record:**

  ```yaml
  example:
    ttl: 60
    type: A
    value: 203.0.113.0
    octodns:
      cloudflare:
        proxied: true
        auto_ttl: true
  ```

### Step 3: Commit Changes

- After editing, provide a commit message, select "Create a new branch", and propose the changes.

![image](https://github.com/user-attachments/assets/668bc9f5-41b6-47f8-9c71-27b3acd23595)

### Step 4: Create a Pull Request

- Click on "Pull requests" in your forked repository.
- Click "New pull request".

![image](https://github.com/user-attachments/assets/2f6b3dc1-e7c4-475f-aee1-0418cce53394)

- Write a description of your changes and submit the PR.

![image](https://github.com/user-attachments/assets/5eeeb454-0807-4c38-8c2f-e2f4977e4ce5)


## Automatic Synchronization

- Once the PR is reviewed and merged, a GitHub Action will automatically sync changes with Cloudflare.

## Advanced Record Types

### A Record

```yaml
example:
  ttl: 300
  type: A
  value: 203.0.113.0
  octodns:
    cloudflare:
      proxied: true
      auto_ttl: true
```

### CNAME Record

```yaml
alias:
  ttl: 300
  type: CNAME
  value: target.domain.com.
  octodns:
    cloudflare:
      proxied: false
      auto_ttl: true
```

### Troubleshooting

- Ensure YAML syntax is correct.
- Check PR comments for any feedback or requested changes.

For further details, refer to the [OctoDNS documentation](https://github.com/octodns/octodns).
