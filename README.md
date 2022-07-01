# WARNING
This was a repo originally only for me, but I realized that it is a nice consolidation of all the files that you would need to flash your keyboard properly, so I made it public am archiving.

# Flashing original bios
1. Flash top chip ` stock/v2.60_patched_signed.bin `
2. Try boot -> if boot move to next heading, else continue
3. Flash bottom chip stock `stock/bottom_stock.bin`
4. Check boot

# Install thinkpad-ec
1. Create bootable disk ec
   ` sudo dd if=patched.x230.img of=/dev/sdx bs=4M status=progress conv=fsync `
2. Boot into bootable disk
   Bios must be set to legacy
3. Go through steps, and hopefully it works

# Go back to coreboot
1. flash top coreboot/top_coreboot.bin
2. maybe flash bottom, it is there to flash coreboot/bottom_coreboot.bin

# Flashrom command
`sudo flashrom -p linux_spi:dev=/dev/spidev0.0,spispeed=512 -c CHIP_NAME -r BINARY_NAME.bin`

top chip = `MX25L3206E/MX25L3208E`
bottom chip = `MX25L6406E/MX25L6408E`
