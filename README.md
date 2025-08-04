# How to Verify Git Commits on GitHub Using GPG Keychain Mac OS

## Verifying your Git commits builds trust and shows authenticity. On GitHub, verified commits display a “Verified” badge to signal they were signed with a trusted GPG key.


### Here’s a step-by-step guide to setting it up on macOS using the GPG Keychain app.

#### Prerequisites

- macOS

- [GPG Suite](https://gpgtools.org/) installed (includes GPG Keychain)

- Git installed

- GitHub account

#### **Step 1:** Generate a GPG Key Using GPG Keychain

1. Open GPG Keychain
2. Click the “New” button.
![Click the “New” button](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kq629eha4js5gn0burbw.png)
3. Fill in your:
- Name (should match your GitHub name
- Email (must match the email you use in your Git commits)
- Key Type: RSA and RSA (default)
- Key Length: 4096 bits (recommended)
- Expiration date: Optional
4. Click “Create Key” and wait until the key is generated.
![Fill in your Details](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3w37zpollylt72nrsgc0.png)

#### **Step 2:** Export Your Public Key
1. Right-click your new key and select “Copy”.
![Right-click your new key and select “Copy”](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/z4uhrhh50tujx3ei7gj5.png)

#### **Step 3:** Add the GPG Key to GitHub
1. Go to GitHub → Settings → SSH and GPG Keys.
2. Click “New GPG Key”.
3. Paste the copied key (or the contents of your exported .asc file).
4. Click “Add GPG Key”.
![Add new GPG key](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cy77td5rifi62aww1e4z.png)

#### **Step 4:** Configure Git to Sign Commits
Find your GPG key ID:

`gpg --list-secret-keys --keyid-format LONG`

Look for the line that looks like this:

`sec   rsa4096/ABCD1234EFGH5678 ..`

Then configure Git:

`git config --global user.signingkey ABCD1234EFGH5678`

`git config --global commit.gpgsign true`

Set Git to use GPG (this path may vary):

`git config --global gpg.program $(which gpg)`


#### **Step 5:** Make a Signed Commit

`git commit -S -m "Your signed commit message"`


Push your code to GitHub. If everything is set up correctly, GitHub will show a Verified badge next to your commit.

![Signed Commits](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xm2p6qtfnrmqybdkj6v8.png)

If you want to learn how to get GitHub achievements! You can learn it step by step here ==> [Get-Github-Achievements-Step-By-Step](https://github.com/4xmen/Get-Github-Achievements)














