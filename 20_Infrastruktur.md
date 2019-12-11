***20_Infrastruktur***
==========================

### Vagrant

Vagrant ist eine Ruby-Anwendung (open-source) zum Erstellen und Verwalten von virtuellen Maschinen (VMs).

Die Ruby-Anwendung dient als Wrapper (engl. Verpackung, Umschlag) zwischen Virtualisierungssoftware wie VirtualBox, VMware und Hyper-V und Software-Konfiguration-Management-Anwendungen bzw. Systemkonfigurationswerkzeugen wie Chef, Saltstack und Puppet.

Wichtig: Die Virtuellen Maschinen entsprechen lauffähigen Servern.

Initialisiert im aktuellen Verzeichnis eine Vagrant-Umgebung und erstellt, falls nicht vorhanden, ein Vagrantfile
    vagrant init


Erzeugt und Konfiguriert eine neue Virtuelle Maschine, basierend auf dem Vagrantfile
    vagrant up


Baut eine SSH-Verbindung zur gewünschten VM auf
    vagrant ssh


Zeigt den aktuellen Status der VM an
    vagrant status


Zeigt die Weitergeleiteten Ports der VM an
    vagrant port


Stoppt die laufende Virtuelle Maschine
    vagrant halt


Stoppt die Virtuelle Maschine und zerstört sie. Am Schluss noch -f (forced) fürs direkte stoppen.
    vagrant destroy



weitere Befehle während dem arbeiten mit Vagrant:

Hinzufügen einer Box zur lokalen Registry
    vagrant box add [box-name]


In der lokalen Registry vorhandene Boxen anzeigen
    vagrant box list



**Synchronisierter Ordner:**

Synchronisierte Ordner ermöglichen es der VM auf Verzeichnisse des Host-Systems zuzugreifen.

    Vagrant.configure(2) do |config|
        config.vm.synced_folder ".", "/var/www/html"  
    end
