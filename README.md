# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Tech stack

- Node v. 20.9.0 at the start of the proyect
- PNPM as package manager v. 8.10.2 at the start of the proyect [Installation Docs](https://pnpm.io/installation)
- Vite for compilation [Docs](https://es.vitejs.dev/guide/)
- React 18

## Cloning a Repository Using SSH

### 1. Generate an ssh key

```sh
ssh-keygen -t ed25519 -C "<comment>"
```

### 2. Press Enter. Output similar to the following is displayed

```sh
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/user/.ssh/id_ed25519):
```

It's recommended to accept the default folder unless you're creating a deploy key or have a specific directory for keys.

### 3. Accept the suggested filename and directory, unless you are generating a deploy key or want to save in a specific directory where you store other keys

### 4. Set a Passphrase (Optional)

```sh
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

### 5. Add the SSH Key to GitHub

- Navigate to your GitHub account settings.
- Click on "SSH and GPG keys".
- Click on "New SSH Key".
- Paste the contents of your public key file, typically located at `/home/user/.ssh/id_ed25519.pub`.
- Assign a descriptive title to the key.

### 6. Create an SSH Config File

Create a config file in your |.ssh| directory to manage your SSH connections:

```sh
touch /home/user/.ssh/config
```

### 7. Edit the SSH Config File

Edit the new config file with the following details, replacing `<your username>` with your actual GitHub username and `<the name of your private key>` with your private key file name (usually `id_ed25519`):

```
#Github account
Host github.com-<your username>
HostName github.com
User git
IdentityFile ~/.ssh/<the name of your private key>
```

For example:

```
#Github account
Host github.com-andresfccy
HostName github.com
User git
IdentityFile ~/.ssh/id_ed25519
```

### 8. Test Your SSH Connection

```
ssh -T git@github-<your username>.com
```

For example:

```
ssh -T git@github-andresfccy.com
```

A successful connection will display a greeting message from GitHub:

```
Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access.
```

### 9. Clone the Repository

Finally, clone the desired repository into your local directory:

```
git clone git@github.com-<your username>:andresfccy/react-challenge.git
```

For example:

```
git clone git@github.com-andresfccy:andresfccy/react-challenge.git
```

---

By following these steps, you should have a cloned repository ready for development on your local machine using SSH for secure communication with GitHub.

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
   parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json'],
    tsconfigRootDir: __dirname,
   },
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list

## Run

- `pnpm install`
- `pnpm run dev`

## Project Structure

The project will adhere to an Atomic Design folder structure.

```sh
src/
├── components/
│   ├── atoms/
│   │   └── ...
│   ├── molecules/
│   │   └── ...
│   ├── organisms/
│   │   └── ...
│   └── templates/
│       ├── DefaultPageTemplate.tsx
│       └── ...
├── pages/
│   ├── HomePage.tsx
│   └── ...
├── App.tsx
├── main.tsx
└── index.css
```
