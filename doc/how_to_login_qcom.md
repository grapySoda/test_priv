# How to Login qcom use QSC-CLI
1. Install curl (if not installed already):
    ```bash
    sudo apt install curl
    ```
2. Download the Debian package for qsc-cli:
    ```bash
    cd <workspace_path>
    curl -L https://softwarecenter.qualcomm.com/api/download/software/qsc/linux/latest.deb -o qsc_installer.deb
    ```
3. Install the qsc-cli Debian package:
    ```bash
    sudo apt update
    sudo apt install ./qsc_installer.deb
    ```
4. Log in to qsc-cli and get PAT:
    ```bash
    qsc-cli login -u <your email>
    qsc-cli pat --get
    ```
    You will see the log like below:
    ```log
    [Info]: Starting qsc-cli version 0.0.0.9
    <your PAT token>
    ```
5. Use your preferred text editor to edit the ~/.netrc file and add the following entries:
    ```bash
    machine chipmaster2.qti.qualcomm.com
    login <your email>
    password <your PAT token>

    machine qpm-git.qualcomm.com
    login <your email>
    password <your PAT token>
    ```

# Reference
- [Qualcomm Linux Build Guide documentation (80-70017-254)](https://docs.qualcomm.com/bundle/publicresource/topics/80-70017-254/build_addn_info.html)