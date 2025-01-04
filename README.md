## Step-by-Step Guide to Upload and Reference Images in a GitHub Repository

- To upload images to GitHub and reference them directly as file paths, you can follow these steps. 
- This ensures that your images are hosted on GitHub itself, rather than relying on external sites, which could expire or go down.

1. **Upload the Image to Your GitHub Repository:**
   - Create a folder named `images`.
   - Go to your GitHub repository where you want to add the images.
   - Click on the `Add file` button in your repository (within the folder where they are organized).
   - Choose `Upload files`.
   - Ensure that the file name contains no spaces. 
   - Drag and drop your image files or use the file picker to select them from your local machine.
   - Commit the files to your repository by entering a commit message and clicking on `Commit changes`.

2. ** Reference the Image Using Relative Paths (for better portability):**

   - Example: If your image is in a folder called `images` and your markdown file is in the root directory, you can reference the image like this:

   ```markdown
   ![Map of Level 1](images/level1-map.png)
   ```

   This method will work as long as the image file is stored within your repository and is in the correct path relative to the Markdown file.

### Example Folder Structure:
If you prefer to organize your files, here’s an example of how your project might look:
```
/my-game-tutorial-repo
    /images
        level1-map.png
        level2-map.png
    README.md
```

In this case, the image in `level1-map.png` would be referenced in `README.md` like this:
```markdown
![Map of Level 1](images/level1-map.png)
```

### Benefits of Using GitHub-hosted Images:
- **Permanent Hosting:** Images are hosted on GitHub itself, so they won't expire unless the repository is deleted or the images are removed.
- **No External Dependencies:** This avoids relying on external image hosting services that may have bandwidth limits or service interruptions.
- **Version Control:** Because the images are part of your repository, they are version-controlled. Any changes you make to the images will be tracked, and users will see the most up-to-date version.

### Note:
- GitHub recommends that images be under **10 MB** for efficient handling within repositories.
- If you're using a lot of large images, consider compressing them or resizing them before uploading to avoid unnecessarily large file sizes.

With this setup, your images will stay safe and directly linked within your repository, ensuring a consistent and reliable experience for anyone viewing your tutorial.


## What if your image is placed in the guide, but is not sized appropriately? 

- To control the **height** and **width** of an image within a Markdown file (like `README.md`), you can't use the standard Markdown syntax alone (which doesn't provide options for dimensions). 
- However, you can still achieve this by embedding HTML directly within the Markdown.

### Solution: Use HTML `<img>` Tag in Markdown

You can use the `<img>` HTML tag, which allows you to specify the `width`, `height`, or both. Here's the modified code:

```markdown
<img src="images/level1-map.png" alt="Map of Level 1" width="600" height="400">
```

### Explanation:
- `src="images/level1-map.png"`: Specifies the path to your image (same as the Markdown format).
- `alt="Map of Level 1"`: Provides alternative text for the image if it fails to load (this is important for accessibility).
- `width="600"`: Sets the width of the image to 600 pixels (you can adjust the value as needed).
- `height="400"`: Sets the height of the image to 400 pixels (you can also adjust this value).

> You can specify either the **width** or **height**, or both. If you set only one of these properties (e.g., `width`), the browser will scale the other dimension to maintain the image's aspect ratio.

### Example with Only Width or Height:

If you want the image to scale proportionally but set a specific width (e.g., 600 pixels), just specify the `width`:

```markdown
<img src="images/level1-map.png" alt="Map of Level 1" width="600">
```

If you'd rather set the height but leave the width proportional, you can do:

```markdown
<img src="images/level1-map.png" alt="Map of Level 1" height="400">
```

### Adjusting Proportions:
- **Both width and height** can be specified if you want to set specific dimensions, but **be mindful** that this may distort the image if the proportions don't match the original.
- If you're unsure about the aspect ratio, it's usually best to specify only one dimension (either width or height) and let the other adjust automatically.

### Final Example (Adjusting Both Dimensions):
Here's a complete example that you might use:

```markdown
<img src="images/level1-map.png" alt="Map of Level 1" width="800" height="533">
```

This will scale the image to 800 pixels in width and 533 pixels in height, keeping the same aspect ratio if the original image's ratio is 4:3.

### Why Use HTML in Markdown?
While Markdown is great for simple formatting, embedding HTML allows you to have more control over your content's layout, such as adjusting the size of images directly within the document.

This approach works well in GitHub README files, as GitHub supports both Markdown and HTML together.

Examples:

1. [Here is a link to the F36F37 jpeg that is clickable](images/F36F37.jpeg)
2. ![Here is the F36F37 jpeg that is viewable in full size](images/F36F37.jpeg)
3. Here is another way to show to map <img src="images/F36F37.jpeg">
4. Here is a way to show the map and also adjust the size <img src="images/F36F37.jpeg" width="600">
