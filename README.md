# Max Photo Bridge Utility
A command line application to archive photo repositories and curate photo collections.  Includes backup utility, inventory, and bit-rot detection to verify that the archive is healthy.

SSDs and NVMe drives aren’t ideal for long‑term archiving because they store data as electrical charge in NAND flash cells, and that charge slowly leaks over time when the drive is unpowered, causing data corruption (bit rot). HDDs, by contrast, store data magnetically and retain it far longer at rest.

⚡ What SSDs and NVMe drives are
SSD (Solid-State Drive): A storage device using NAND flash memory. No moving parts, fast, durable for everyday use.

NVMe SSD: Not a different type of memory — it’s an SSD that uses the NVMe protocol over PCIe, making it much faster than SATA SSDs. But the underlying NAND flash technology (TLC, QLC, etc.) is the same.

🧬 Why SSDs/NVMe drives are not ideal for long-term archiving
1. Charge leakage in NAND flash (bit rot)
NAND cells store data as trapped electrons. Over time, the insulating layer degrades and electrons leak, causing the stored bits to drift and eventually flip.

SSDs can lose data within a few years if left unpowered, especially in warm environments. 

Flash memory requires periodic power‑on cycles to refresh cell voltages. 

2. More bits per cell = less stability
Modern consumer SSDs use TLC or QLC NAND:

TLC: 3 bits per cell — decent endurance but still vulnerable over long unpowered periods. 

QLC: 4 bits per cell — much smaller voltage margins, meaning faster charge leakage and higher risk of corruption. 

This makes high‑capacity consumer NVMe drives especially risky for archival storage.

3. Controllers depend on DRAM or host memory
DRAMless SSDs (common in budget NVMe drives) rely on Host Memory Buffer (HMB).
If the mapping tables degrade or the controller fails, the entire drive can become unreadable suddenly — not gradually. 

4. Temperature sensitivity
SSD data retention time drops sharply at higher temperatures.
Warm storage environments accelerate charge leakage and can wipe an SSD faster. 

5. Unpowered retention is short
Many SSDs need to be powered on every 6–24 months to refresh data.
Some sources recommend refresh cycles as often as every 6 months for safety. 

🖼️ Why this matters for photo archives
Image files (RAW, TIFF, JPEG) are large and sensitive to corruption:

Even a single flipped bit can visibly distort a photo. 

Silent corruption may go unnoticed until years later when the file becomes unreadable.

SSD/NVMe drives are optimized for speed, not archival stability.

🧱 Better long‑term storage options
For multi‑year or decade‑scale archiving:

Enterprise‑grade HDDs (magnetic storage retains data for decades).

NAS with RAID + scrubbing (ZFS, Btrfs, or Synology Hybrid RAID).

Cloud cold storage (Backblaze B2, Amazon Glacier) as offsite redundancy.

✔ Summary
SSD and NVMe drives are excellent for active use, but for long‑term archiving they have fundamental weaknesses:

Data stored as electrical charge slowly leaks.

Modern high‑density NAND (TLC/QLC) accelerates bit rot.

Unpowered retention is short (months to a few years).

Temperature and controller design further reduce reliability.

For long-term photo archives, HDDs or NAS systems remain far safer.
