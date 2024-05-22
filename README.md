**The url to the repository has been updated! Please re-run step 2 below to use the new paths**

RStudio does not provide an official repository for Debian/Ubuntu. This is an unofficial apt repository for RStudio. This repository serves the latest official `.deb` from RStudio. All files are checked against the RStudio GPG keys. The repo is automatically updated twice per day.

## Installation Instructions

**Step 1:** Add my GPG certificate to your keyrings folder. This does **not** automatically trust my key for anything.

```
sudo mkdir -p /etc/apt/keyrings && wget -qO- https://mirror.mwt.me/my/gpgkey | sudo tee /etc/apt/keyrings/mwt.asc > /dev/null
```

**Step 2:** Add this to your list of repositories. This step tells apt to use my key to check the repo.

```
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/mwt.asc by-hash=force] https://mirror.mwt.me/rstudio/deb/jammy jammy main" | sudo tee /etc/apt/sources.list.d/mwt.list
```

## Using with my Zoom Repository

To use this with my Zoom repository, also run

**Step 3:** Add this to your list of repositories. This step tells apt to use my key to check the repo.

```
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/mwt.asc by-hash=force] https://mirror.mwt.me/zoom/deb any main" | sudo tee -a /etc/apt/sources.list.d/mwt.list
```

## Upgrade notice

This repostitory used to be at `https://mirror.mwt.me/my/deb`. For simplicity and consistancy with the other repos on `mirror.mwt.me`, I have moved the repo to `https://mirror.mwt.me/rstudio/deb`. To upgrade, just rerun Step 2 above.
