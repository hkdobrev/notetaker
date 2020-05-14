# 📝 Notetaker
![reviewdog](https://github.com/hkdobrev/notetaker/workflows/reviewdog/badge.svg) [![Static: Active Development](https://img.shields.io/badge/Status-Active%20Development-important.svg?style=flat)](https://github.com/hkdobrev/notetaker)


Note taker for notes, blog posts, todo lists from the command line.

The notetaker project aims to help people manage their notes as easily as writing Markdown in their favourite editor.

**Main ideas behind notetaker**:

- Edit your own files with your favourite program. You can use vim, VS Code, Sublime Text, Caret, Notable as long as you save them in Markdown files with the `.md` extension.
- Organise your notes in folders to your liking, you can have notes for projects, journals, essays in folders and files based on your own preference.
- Do not depend on a central server to browse and edit your notes.
- Do not depend on a proprietary desktop program to browse and edit your notes.
- You do your own version control of notes, but if you use Git notetaker would leverage that to extract useful information.
- Write action items in your notes using GitHub-Flavoured Markdown checklists and notetaker would find them all for you.
- Publish your markdown files with notes and todos to GitHub and you would have easy access from your browser or mobile phone with ability to mark todo items as done.
- Tags, blog posts and encryption are coming in the future.

## Install

In the future, notetaker could be submitted to package managers for easy install.
For now, clone the repo and point your `PATH` to the folder where you've cloned it or symlink the binaries where you'd like:

```shell
git clone git@github.com:hkdobrev/notetaker.git
```

Create a folder for your notes. By default it is `~/notes`, but it could be configured via `NOTES_PATH` environment variable.
```shell
mkdir ~/notes
```
or
```shell
mkdir ~/Documents/my_notes
echo "export NOTES_PATH=~/Documents/my_notes" >> ~/.bash_profile
```

## Usage

Run `notes --help` for command-line usage:
```shell
$ notes --help
Usage: notes [--help | -h | -?] <command> [<args>]

Subcommands:
    new                Create a new note with your EDITOR
    list               List all found notes
    todos              List todo items from all of your notes
    find               Find notes with matching title
    search             Search notes for text

Options:
    -h, -?, --help     Output usage for notes or a subcommand
```

### Create a note

<details>
<summary>Just save a new Markdown file with the `.md` extension in your notes directory (<code>~/notes</code> by default):</summary>
<pre><code class="language-shell">
cat > ~/notes/journal-log.md &lt;&lt;EOF
# My first journal log
Here are some action items:
- [ ] Install notetaker
- [ ] Check out notes todos
EOF
</code></pre>
</details>

### TODOs

Running `notes todos` would find and show you the todos not marked as done from all of your notes.

```shell
$ notes todos

journal-log.md:

  - [ ] Check out notes todos
```

`notes todos --done` would list only the checked todo items
`notes todos --all` would give you both done and not done todos

Run `notes todos --help` for all usage details.

## Contributing

Browse [current issues first](https://github.com/hkdobrev/notetaker/issues) and [open an issue](https://github.com/hkdobrev/notetaker/issues/new) for a question, suggestions or to discuss a bigger change. For any concrete suggestions, open a pull requesst.

Public list of potential features would be coming soon on GitHub as issues, milestones and projects.

## License

The notetaker project is licensed under the [Unlicense license](LICENSE) which is equivalent to the public domain.
