## Here you can go to the website: [:)](https://nico-shock.github.io/Arch-Linux-on-Nvidia-V2.1/)

### **Make sure this is only indeed for an info like dokumentation list not a guide or something.**


### Here is V1: [:(](http://web.archive.org/web/20250807183030/https://nico-shock.github.io/Arch-Linux-on-Nvidia/)

# Changelog V2 → V2.1 (only for me)

**Meta**  
- Title & H1: changed "V2" → "V2.1"  
- Footer year: changed 2025 → 2026  

**Design (complete overhaul)**  
- Background: #151517 → pure black #000000  
- Font: Inter/Segoe UI → Lora (body) + JetBrains Mono (code blocks), loaded via Google Fonts  
- Body color: #e0e0e0 → #a8a8b0; font-size 17px → 16px; added line-height: 1.75  
- Container: max-width 960px → 860px; removed border-radius and overflow: hidden; padding 20px → 40px 24px  
- Header/footer: centered → left-aligned; added border separators; footer text muted #444450  
- H1/H2/H3: split into individual rules with sizing, letter-spacing, border-bottom on H2  
- Links: #bb86fc → #9b59f7; hover underline → border-bottom + color #b87dff  
- Table: padding → 6px 14px; border #333 → #111115; TH uppercase + muted; added tr:hover highlight  
- Code blocks: background #212124 → #080808; added border: 1px solid #111115; removed border-radius; added JetBrains Mono, font-size 0.82em, color #b0b0bc  
- Copy button: added border; background #333 → #080808; color muted; border-radius removed; width → 86px; height → 42px; hover shows purple accent on text + border  
- .highlight: #7c3aed → #9b59f7  
- .command-target: #06b6d4 → #6ab0d4; added monospace font  
- .optional: #10b981 → #4a7a5a; .not-recommended: #f44336 → #8a3a3a  
- Added custom scrollbar (4px, purple on hover)  
- Added box-sizing: border-box global reset  

**Navigation**  
- Added fixed left-side nav dots (one per section, 7×7px rounded squares, no transition/animation)  
- Added back-to-top circle button above dots  
- Dot tooltip on hover shows section title to the right  
- Active dot highlights purple instantly on click; IntersectionObserver updates on manual scroll  
- Race condition fix: unique lockToken per click prevents rapid-click flicker  
- All TOC anchor links use smooth scroll + instant dot update  
- Nav hidden below 1060px viewport width  

**Copy button behavior**  
- Changed innerText → textContent  
- "Copied!" shows in purple with purple border  
- resets after 2s without layout shift  

**Step 9 — Make Downloads Faster**  
- Added reflector install + `reflector --latest 20 --protocol https --sort rate --save /etc/pacman.d/mirrorlist`  

**Step 10 — Install Linux Base System**  
- Added amd-ucode to pacstrap (replace with intel-ucode for Intel CPUs)  

**Step 11 — Swapfile**  
- Added note: 64 GB+ RAM systems should use min. 8 GB, recommended 16 GB swap (especially for hibernation)  

**Step 15 — Install Bootloader**  
- Added initrd /amd-ucode.img before initramfs line in boot entry  
- Added `nvidia-drm.modeset=1` and `nvidia_drm.fbdev=1` to kernel options line  
- Added `echo "timeout 3" >> /boot/loader/loader.conf` with note that 0 skips the menu entirely  

**Step 16 — Install a Desktop Environment**  
- Split into two subsections: GNOME (existing) and KDE Plasma (new: plasma konsole ark dolphin sddm + systemctl enable sddm)  
- Removed outdated closing paragraph  

**Step 17 — Install Required and Recommended Stuff**  
- Renamed: "Recommended and Required" → "Required and Recommended"  
- Required command: removed dolphin; reordered GNOME packages to end of list  
- Added warning: do not install GNOME packages on KDE Plasma, use kate and dolphin instead  
- Added subsection "Required Stuff for KDE Plasma": `sudo pacman -S dolphin kate`  

**Step 18 — Install Nvidia Drivers**  
- Changed nvidia-dkms → nvidia-open-dkms  

**Steps 19–21 — New sections added**  
- Added Step 19: NVIDIA Decoding Support — `libva-nvidia-driver vdpauinfo libva-utils`  
- Added Step 20: Install Video Player Acceleration Plugins — `gst-plugins-good gst-plugins-bad gst-libav`  
- Added Step 21: Install Vulkan Libraries — `lib32-vulkan-icd-loader`  
- Steps renumbered: all steps after 18 shifted +3; guide now ends at step 34 (was 33)  

**Removed**  
- Step "Settings needed to Install the Open Nvidia Drivers from CachyOS" — deleted entirely  
- Step "Install Open Nvidia Driver (Optional)" (linux-cachyos-nvidia-open) — deleted entirely  

**Step 29 — CachyOS Gaming Meta**  
- Added note: package includes steam, lutris and more; no additional gaming packages needed  

**Step 31 — Bootloader Config**  
- Renamed: "Bootloaderconfig" → "Bootloader Config"  

**Requirements**  
- Fixed typo: "recommendet" → "recommended"
