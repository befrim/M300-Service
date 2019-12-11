***10_Toolumgebung***
==========================

### SSH-Key

Erstellung eines SSH Keys wird folgt gemacht, dabei wird direkt ein SSH Key erstellt:

  ssh-keygen -t rsa -b 4096 -C "befrim@hotmail.ch"

danach kann man ein Passwort für den SSH Key erstellt werden.


SSH Agent starten: $ eval "$(ssh-agent -s)"

Ab 10.13 muss man die Config-Datei anpassen, die passt man wie folgt an:

  sudo nano ~/.ssh/config
  
  Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa

Hat man es angepasst, kann man den Schlüssel dann hinzufügen:

  ssh-add -k ~/.ssh/id_rsa

Danach muss man im GitHub unter *Settings* den SSH-Key hinzufügen.

  cat ~/.ssh/id_rsa.pub



### Git-Client

Client installieren ab Webseite.

Danach konfigurieren:

  git config --global user.name "patriksantos"
  git config --global user.email "psantos@bluewin.ch"

Danach kann man sein Repository klonen und aktualisieren, das passiert so:

Neuer Ordner erstellen und mit **cd** Verzeichnis ändern.

Danach können wir unser Repostory klonen:

  git clone github.com/patriksantos/M300-Services.git

mit **git pull** können wir es aktualisieren (den lokalen Ordneer) und mit **git status** prüfen wir den Status;

mit **git add -A** können wir alle Dateien zu unser Updateliste hinzufüfen;

mit **git commit -m "Kommentar hinzufügen"** kommentieren wir unser Upload;

und mit **git push** pushen wir den Upload.



### Vagrant

Vagrant ist eine freie Ruby-Anwendung zum Erstellen und Verwalten virtueller Maschinen. Vagrant ermöglicht einfache Softwareverteilung insbesondere in der Software- und Webentwicklung und dient als Wrapper zwischen Virtualisierungssoftware wie VirtualBox, KVM/QEMU, VMware und Hyper-V und Software-Configuration-Management-Anwendungen beziehungsweise Systemkonfigurationswerkzeugen wie Chef, Saltstack und Puppet.

Um eine neue VM einzurichten brauchen wir einen leeren Ordner.

  vagrant init ubuntu/xenial64        //Vagrantfile erzeugen
  vagrant up --provider virtualbox    //Virtuelle Maschine erstellen & starten

Danach:

  cd Pfad/zu/meiner/Vagrant-VM      //Zum Verzeichnis der VM wechseln
  vagrant ssh                       //SSH-Verbindung zur VM aufbauen

  Anschliessend können ganz normale Bash-Befehle abgesetzt werden:

  ls -l /bin  //Bin-Verzeichnis anzeigen
  df -h       //Freier Festplattenspeicher
  free -m     //Freier Arbeitsspeicher

Um eine VM zu löschen geben wir den Befehl "$ vagrant destroy -f" ein.

