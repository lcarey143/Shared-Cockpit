# How to Add a Logo/Icon to Your Application

This guide explains how to add a custom icon (logo) to the Shared Cockpit executable and installer.

## Step 1: Create or Get an Icon File

You need an `.ico` file (Windows icon format). You can:

### Option A: Convert an Image to .ico

1. **Find or create your logo/image** (PNG, JPG, etc.)
   - Recommended size: 256x256 pixels or larger
   - Square format works best

2. **Convert to .ico format**:
   - Use an online converter: https://convertio.co/png-ico/ or https://www.icoconverter.com/
   - Or use a tool like:
     - **IcoFX** (free): https://icofx.ro/
     - **GIMP** (free): https://www.gimp.org/ (can export as .ico)
     - **Paint.NET** (free): https://www.getpaint.net/ (with plugin)

3. **Save as `icon.ico`** in your project folder (same folder as `main.py`)

### Option B: Use a Simple Icon Generator

1. Visit: https://www.favicon-generator.org/ or https://realfavicongenerator.net/
2. Upload your image
3. Download the .ico file
4. Rename it to `icon.ico` and place in your project folder

## Step 2: Place the Icon File

1. **Save `icon.ico`** in your project root folder:
   ```
   Shared cockpit/
   ├── icon.ico          ← Place it here
   ├── main.py
   ├── build_exe.py
   └── ...
   ```

## Step 3: Rebuild the Executable

1. **Run the build script**:
   ```bash
   python build_exe.py
   ```

2. The build script will automatically detect `icon.ico` and use it

3. **Your new .exe will have the icon!**

## Step 4: Update the Installer (Optional)

If you're creating an installer with Inno Setup:

1. Make sure `icon.ico` is in your project folder
2. The `SharedCockpit.iss` file is already configured to use it
3. Build the installer in Inno Setup Compiler

## Icon Requirements

- **Format**: `.ico` (Windows Icon format)
- **Recommended sizes**: 16x16, 32x32, 48x48, 256x256 (multi-resolution .ico files work best)
- **Location**: Project root folder (same as `main.py`)
- **Name**: `icon.ico` (exact name)

## Tips

- **Multi-resolution icons**: Create an .ico file with multiple sizes (16, 32, 48, 256) for best quality
- **Simple designs**: Icons look better when simple and recognizable at small sizes
- **Transparency**: .ico files support transparency - use PNG with transparency when converting

## Testing

After building:
1. Check the `.exe` file in `dist/SharedCockpit.exe` - it should show your icon
2. Check the installer (if created) - it should also show your icon

## Troubleshooting

**Icon not showing?**
- Make sure the file is named exactly `icon.ico` (case-sensitive on some systems)
- Make sure it's in the project root folder
- Try rebuilding: `python build_exe.py`
- Check that the .ico file is valid (try opening it in Windows)

**Icon looks blurry?**
- Use a higher resolution source image (256x256 or larger)
- Create a multi-resolution .ico file with multiple sizes
