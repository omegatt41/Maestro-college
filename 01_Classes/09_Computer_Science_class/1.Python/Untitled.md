
## Programming Note Template



````markdown
---
created: <% tp.file.creation_date() %>
modified: <% tp.date.now("YYYY-MM-DD HH:mm") %>
tags: programming/<% tp.file.cursor(1) %>
language: 
status: seedling
---

# <% tp.file.title %>

## 📝 Description
> Brief overview of what this code/concept does.

## 💻 Code Snippet
```<% tp.file.cursor(2) %>
// Your code here
````

## 🛠️ Usage / Implementation

- Step 1:
- Step 2:

## 🔗 Resources

- Official Documentation
- Stack Overflow Reference

---

## 🧠 Related Notes

- [[MOC - Programming]]
- [[<% tp.date.now("YYYY-MM-DD") %>]]

```unset

### Key Components for Programmers
*   **Dynamic Metadata**: Uses `<% tp.file.creation_date() %>` to automatically log when you started the note.
*   **Cursor Focus**: The `<% tp.file.cursor(1) %>` tags allow you to immediately start typing in specific spots (like tags or code blocks) using a hotkey to jump between them.
*   **Documentation Links**: Including a dedicated section for external resources like [GitHub](https://github.com) or documentation prevents you from having to search for the same solution twice.
*   **Organization**: Many developers use a "How to... in [Language]" naming convention for their notes to make them easily searchable later (e.g., "How to center a div in CSS").

### Setup Tips
1.  **Enable Templater**: Install it from the Community Plugins and ensure "Trigger Templater on new file creation" is toggled **on** in its settings.
2.  **Folder Templates**: You can set Obsidian to automatically apply this specific template whenever you create a new file inside a `/Programming` folder.
3.  **Hotkeys**: Map the "Templater: Insert template" command to a shortcut like `Alt+E` to quickly drop this structure into any existing note.

Would you like help setting up **Dataview queries** to automatically list all your snippets by language?
```

  

[1] [https://forum.obsidian.md](https://forum.obsidian.md/t/programmer-how-do-you-format-your-programming-notes/20494#:~:text=Programmers%20can%20format%20their%20programming%20notes%20in,in%20Obsidian%20*%20Linking%20notes%20to%20source)

[2] [https://amyjuanli.medium.com](https://amyjuanli.medium.com/use-obsidian-templater-to-automate-our-note-taking-system-beginners-f6c507258427)

[3] [https://github.com](https://github.com/silentvoid13/Templater)

[4] [https://www.reddit.com](https://www.reddit.com/r/ObsidianMD/comments/wwsvhm/how_to_take_fleeting_programming_notes_in_obsidian/)

[5] [https://forum.obsidian.md](https://forum.obsidian.md/t/add-timestamps-and-datestamps-to-notes-w-only-core-plugins/18973#:~:text=You%20can%20automatically%20insert%20the%20date%20or,need%20the%20Templater%20or%20Natural%20Language%20plugins.)

[6] [https://forum.obsidian.md](https://forum.obsidian.md/t/is-there-a-way-to-create-a-new-unique-note-in-the-current-folder/70469#:~:text=This%20can%20surely%20be%20accomplished%20with%20a,Templater%20community%20plugin%20%28set%20in%20the%20settings%29.)

[7] [https://forum.obsidian.md](https://forum.obsidian.md/t/review-old-notes-aging-notes-spaced-repetition/40562#:~:text=Copy%20and%20paste%20the%20template%20code%20into%20your%20new%20template%20note.)

[8] [https://forum.obsidian.md](https://forum.obsidian.md/t/getting-an-error-with-templater-but-the-cause-nor-the-solution-is-clear/67471#:~:text=Templater%20is%20one%20of%20them%20%28%20plugins,be%20where%20Templater%20looks%20for%20its%20templates.)