# Extend `/var` LVM Partition After Increasing AWS EBS Volume

## 1. Increase EBS Volume in AWS

Open [Amazon EC2 Console](https://console.aws.amazon.com/ec2/?utm_source=chatgpt.com)

Go to:

* EC2
* Volumes
* Select attached EBS volume
* Actions → Modify Volume
* Increase size (example: 20GB → 30GB)
* Save changes

Wait until volume state becomes:

* `optimizing`
* or `completed`

---

# 2. Verify New Disk Size

bash id="m4p8q1"
lsblk


Example:

bash id="u2r5k9"
nvme0n1  30G


---

# 3. Extend Partition

Extend LVM partition (`p4` in this case):

bash id="c7n1v5"
growpart /dev/nvme0n1 4


Verify:

bash id="z9m3q2"
lsblk


Now partition should also show increased size.

Example:

bash id="w5r8d1"
nvme0n1p4  29.4G


---

# 4. Resize Physical Volume (PV)

bash id="f1k6p7"
pvresize /dev/nvme0n1p4


---

# 5. Verify Free Space in Volume Group

bash id="x8q2m4"
vgs


You should now see free PE/space available.

---

# 6. Extend Logical Volume (`/var`)

Example: add 10GB to `/var`

bash id="r3v7n9"
lvextend -L +10G /dev/RootVG/varVol


Verify LV size:

bash id="j6m1p5"
lsblk


Example:

bash id="a4k8d2"
RootVG-varVol 12G


---

# 7. Check Filesystem Type

bash id="n5q7r3"
df -Th /var


Example:

bash id="v2p4m8"
xfs


---

# 8. Grow Filesystem

If filesystem is `xfs`:

bash id="g1d9k6"
xfs_growfs /var


If filesystem is `ext4`:

bash id="t8m3q1"
resize2fs /dev/RootVG/varVol


---

# 9. Verify Final Size

bash id="y7p2v4"
df -h /var


Example:

bash id="k9r5m1"
Filesystem                Size  Used Avail Use%
/dev/mapper/RootVG-varVol  12G


Now `/var` has additional storage available for Docker.
