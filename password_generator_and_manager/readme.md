# Password Generator & Manager

A simple desktop app built with Python and **Tkinter** that generates strong,
random passwords and stores your login credentials locally. Generated passwords
are copied to your clipboard automatically so you can paste them wherever you
need.

![logo](logo.png)

## Features

- **Random password generation** — creates a strong password mixing uppercase
  and lowercase letters, numbers, and symbols.
- **Auto copy to clipboard** — the generated password is copied instantly
  (via `pyperclip`), ready to paste.
- **Save credentials** — stores the website, email/username, and password to a
  local `data.txt` file.
- **Input validation** — warns you if the website or password field is left
  empty before saving.
- **Confirmation prompt** — asks you to confirm the details before writing them
  to the file.

## How It Works

The app opens a small GUI window with three fields:

| Field            | Description                                    |
|------------------|------------------------------------------------|
| Website          | The site the credentials are for               |
| Email/Username   | Your login email or username (pre-filled)      |
| Password         | The password (type your own or generate one)   |

### Generating a password

1. Click **Generate Password**.
2. A random password is created from:
   - 8–10 letters (mixed case)
   - 2–4 symbols
   - 2–4 numbers
3. The characters are shuffled, shown in the password field, and copied to your
   clipboard.

### Saving a password

1. Fill in the **Website** field (and optionally adjust the email/username).
2. Generate or type a password.
3. Click **Add**.
4. Confirm the details in the popup.
5. The entry is appended to `data.txt` in the format:

   ```
   website | email | password
   ```

If the website or password field is empty, the app shows a warning instead of
saving.

## Requirements

- Python 3.8 or newer
- [`pyperclip`](https://pypi.org/project/pyperclip/) (for clipboard support)
- `tkinter` (included with most Python installations)

## Installation

Using **Poetry** (recommended, config already included):

```bash
poetry install
```

Or install the dependency manually with pip:

```bash
pip install pyperclip
```

## Usage

Run the app from the project folder:

```bash
python main.py
```

Make sure `logo.png` is in the same directory as `main.py`, since the app loads
it for the window logo.

## Project Structure

```
password_generator_and_manager/
├── main.py          # Application code (UI + logic)
├── data.txt         # Saved credentials (created/appended at runtime)
├── logo.png         # Logo shown in the app window
├── pyproject.toml   # Poetry project config & dependencies
└── readme.md        # This file
```

## Notes & Limitations

- Passwords are stored in **plain text** in `data.txt`. This is fine for
  learning/demo purposes, but do not use it for real sensitive accounts without
  adding encryption.
- The email/username field is pre-filled with a default value in `main.py` —
  change it there to your own if you like.
