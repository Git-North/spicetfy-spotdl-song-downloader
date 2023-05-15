# spicetfy-spotdl-song-downloader

The purpose of this repo is to download spotify playlist to your pc using spotdl

I was thinking of making a spotdl gui but then I found spicetify to be more convinient
The code is not even ready yet so ill show the dependecys
- Spicetify (Obviously)
- Git for installing
- Spotdl (it's in the name)
- ffmpeg (Spotdl dependency)
- python (Spotdl dependency)

I will leave a choco script for packages above

## installing choco if not already present

Run this in powershell with admin :)

```
    try{
        Write-Host "Checking if Chocolatey is Installed..."

        if((Test-WinUtilPackageManager -choco)){
            Write-Host "Chocolatey Already Installed"
            return
        }
    
        Write-Host "Seems Chocolatey is not installed, installing now?"
        #Let user decide if he wants to install Chocolatey
        $confirmation = Read-Host "Are you Sure You Want To Proceed:(y/n)"
        if ($confirmation -eq 'y') {
            Set-ExecutionPolicy Bypass -Scope Process -Force; Invoke-Expression ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1')) -ErrorAction Stop
            powershell choco feature enable -n allowGlobalConfirmation
        }
    }
    Catch{
        throw [ChocoFailedInstall]::new('Failed to install')
    }

```
## and the packages
```

choco install spicetify-cli -y
choco install git.install -params /NoShellIntegration -f
choco install ffmpeg -y
choco install python -y
pip install --upgrade pip
pip install spotdl

```
 > On some systems you might have to change `pip` to `pip3`.

You could always just install these "the normal way" im just putting it out there 
