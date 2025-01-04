## Step-by-Step Guide to Upload and Reference Images in a GitHub Repository

- Goal is to upload images to GitHub and reference them directly as file paths. This ensures that images are hosted on GitHub itself, rather than relying on external sites, which could expire or go down.

1. **Upload the Image to Your GitHub Repository:**
   - If not already done, create a folder named `images`.
   - Click on the `Add file` button.
   - Choose `Upload files`.
   - Ensure that the file name contains no spaces. 
   - Drag and drop your image files or use the file picker to select them.
   - Commit the files to your repository by entering a commit message and clicking on `Commit changes`.

2. Example Folder Structure:

```
/my-game-tutorial-repo
    /images
        level1-map.png
        level2-map.png
    README.md
```

In this case, the image in `level1-map.png` would be referenced in `README.md` like this:
```markdown
![Map of Level 1](/images/level1-map.png)
```

## What if your image is placed in the guide, but is not sized appropriately? 

- To control the **height** and **width** of an image within a Markdown file (like `README.md`), you can't use the standard Markdown syntax alone (which doesn't provide options for dimensions). 
- However, you can still achieve this by embedding HTML directly within the Markdown.

### Solution: Use HTML `<img>` Tag in Markdown, but be sure to use the Relative Path from the Root Directory since we are keeping all images in one image folder at the root.

You can use the `<img>` HTML tag, which allows you to specify the `width`, `height`, or both. Here's the modified code:

```markdown
<img src="/images/level1-map.png" alt="Map of Level 1" width="600" height="400">
```

### Explanation:
- `src="/images/level1-map.png"`: Specifies the path to your image (same as the Markdown format).
- `alt="Map of Level 1"`: Provides alternative text for the image if it fails to load.
- `width="600"`: Sets the width of the image to 600 pixels (you can adjust the value as needed).
- `height="400"`: Sets the height of the image to 400 pixels (you can also adjust this value).

> You can specify either the **width** or **height**, or both. If you set only one of these properties (e.g., `width`), the browser will scale the other dimension to maintain the image's aspect ratio.

- If you're unsure about the aspect ratio, it's usually best to specify only one dimension (either width or height) and let the other adjust automatically.
  
```markdown
<img src="/images/level1-map.png" alt="Map of Level 1" width="600">
```

### Why Use HTML in Markdown?
While Markdown is great for simple formatting, embedding HTML allows you to have more control over your content's layout, such as adjusting the size of images directly within the document.

This approach works well in GitHub README files, as GitHub supports both Markdown and HTML together.

Examples:

1. Simple clickable link: [Here is a link to the F36F37 jpeg that is clickable](/images/F3637.jpeg)
2. HTML Image   
   ![Here is the F36F37 jpeg that is viewable in full size](/images/F3637.jpeg)
4. Markdown Image   
   <img src="/images/F3637.jpeg">
5. Here is a way to show the map and also adjust the size   
    <img src="/images/F3637.jpeg" width="600">
