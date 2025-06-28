# Contributing to HUST-China-2025

## Getting started

You can choose to contribute to this project in two ways:

- [Contribute online](#contribute-online): Make changes directly in the [GitHub Dev](https://github.dev/Lucas04-nhr/HUST-China-2025) or [iGEM GitLab Web IDE](https://gitlab.igem.org/-/ide/project/2025/hust-china/edit/main/-/) web interface.
- [Contribute locally](#contribute-locally): Clone the repository to your local machine, make changes, and push them back to GitHub.

> [!TIP]
> - Due to the low-speed of the iGEM GitLab Web IDE, we recommend using the [GitHub Dev](https://github.dev/Lucas04-nhr/HUST-China-2025) web interface for editing files.
> - You can also enter the iGEM GitLab Web IDE by clicking the "Edit" button on the top right corner of any file in this repository, then click the "Open in Web IDE" button.

### Contribute Locally

You should probably only edit the files inside the folder `wiki`. To contribute to this project locally, please follow these steps:

1. **Fork the Repository**: Click the "Fork" button at the top right of this repository to create your own copy.

2. **Clone Your Fork**: Clone your forked repository to your local machine using:
  ```bash
  git clone https://github.com/<your-username>/HUST-China-2025.git
  ```

3. **Create a New Branch**: Create a new branch for your changes:
  ```bash
  git checkout -b <branch-name>
  ```

> [!WARNING]
> Don't push to the `main` branch directly, use a merge request instead. All changes pushed to the `main` branch will be abandoned.

4. **Make Your Changes**: Implement your changes or additions.

5. **Commit Your Changes**: Commit your changes with a meaningful commit message:
  ```bash
  git add .
  git commit -m "Description of your changes"
  ```

6. **Push to Your Fork**: Push your changes to your forked repository:
  ```bash
  git push origin <branch-name>
  ```

7. **Submit a Pull Request**: Navigate to the original repository and click "New Pull Request". Select your branch and submit the PR to the `main` branch.

Your contribution will be reviewed, and feedback may be provided. Thank you for contributing!

> [!NOTE]
> 
> Please use the following commit message format when contributing:
> 
> ```
> <type>(<scope>): <short description>
> ```
> 
> - **type**: The type of change (e.g., `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, etc.).
> - **scope**: The scope of the change (e.g., `ci`, `docs`, `core`, etc.).
> - **short description**: A brief description of the change.
>
> For example:
> ```
> refactor(ci): update CI configuration to use Ruby for Jekyll deployment
> ```
>
> This format helps maintain a consistent commit history and improves readability.

### Contribute online

You should probably only edit the files inside the folder `wiki`. To contribute to this project locally, please follow these steps:

1. Open the Web IDE

2. Follow the instructions in [Contribute locally](#contribute-locally) to use `main` branch and make your changes.

---

See [GitHub Contributing Graph](https://github.com/Lucas04-nhr/HUST-China_2025/graphs/contributors) for more details of our contributors.