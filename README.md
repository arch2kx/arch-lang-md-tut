# Set Any Thai font (or other lang) as default with Fontconfig on Arch
© 2025 Arch Kun — Do not redistribute without this label. All rights reserved.

NOTE: You need to create or modify a fontconfig file to make Sarabun or any other compatible Thai font the default.

1. Open or create font config file in nano (or vim):
```
nano ~/.config/fontconfig/fonts.conf
```
2. Add the following XML block to set any Thai font (e.g. Sarabun) as the default Thai font:
```xml
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <match>
        <test name="lang" compare="contains">
            <string>th</string>
        </test>
        <edit name="family" mode="assign" binding="strong">
            <string>Sarabun</string>
        </edit>
    </match>
</fontconfig>
```

3. Save file and exit (Ctrl+X or :wq in vim)

4. Update font cache with:
```bash
fc-cache -fv
```

5. Verify changes
Make sure the font is installed
```bash
fc-match :lang=th
```

6. Restart your Arch distro and hope that the fonts work
