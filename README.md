# Wireshark-2-Mavlink_Tutorial
Tutorial completo de instalação das ferramentas necessárias para visualizar a comunição Mavlink entre Ground Control Station e Drone.

## Configurando acesso remoto(SSH)
Utilizando o comando `ssh` você pode acessar remotamente o drone através da rede de internet, precisando saber o usuário e o IPv4 do drone para acessá-lo, exemplo: `ssh pi@192.168.0.100`. \
O usuário padrão da Raspberry é `pi`, para descobrir o IPv4 é necessário olhar a lista DHCP do seu roteador: \
<img width="699" height="424" alt="image" src="https://github.com/user-attachments/assets/993b32a1-f1a4-4dc7-8f31-804941840a9f" /> \
Ao conectar-se pela primeira vez, você vai ver a seguinte mensagem: \
<img width="655" height="452" alt="image" src="https://github.com/user-attachments/assets/76b6fdfe-18b2-4a9b-bff9-9de57bb41f6f" /> \
Digite `yes` e prossiga. \
Você saberá que está conectado no drone quando a interface mostrar o nome de usuário e o Hostname aqui: \
<img width="654" height="104" alt="image" src="https://github.com/user-attachments/assets/9b45ad39-ff1f-4768-9f60-7b1a2c14599b" /> \
Para abrir a porta de acesso de conexão entre a GCS e o drone é necessário rodar o script `mavlink.sh` utilizando o comando: `./mavlink.sh`, isso vai trancar seu terminal no processo.

## Instalando Ground Control Station(GCS)

Seguir tutorial de instalação [daqui](https://docs.qgroundcontrol.com/master/en/qgc-user-guide/getting_started/download_and_install.html).\
Depois de instalado, para conectar-se no drone você deve ir em:\
<img width="200" height="218" alt="image" src="https://github.com/user-attachments/assets/073a4d7a-e403-4d5a-bfb2-93d25eaf6532" />\
Application Settings\
<img width="195" height="244" alt="image" src="https://github.com/user-attachments/assets/ee826a4b-d1fb-433a-b723-2df6194b53d2" />\
Comm Links\
<img width="325" height="326" alt="image" src="https://github.com/user-attachments/assets/2627965b-be67-4095-a653-cfde358a548d" />\
Add\
<img width="386" height="71" alt="image" src="https://github.com/user-attachments/assets/a24f3538-249d-4484-b419-60d32eeca839" />\
Coloque o nome que você preferir, mude Type para UDP e coloque o IPv4 do drone seguido da porta `14550`\
<img width="442" height="392" alt="image" src="https://github.com/user-attachments/assets/ab9d9fa7-a54f-46eb-9b03-0b6edc05d78e" />

## Instalando Wireshark

Seguir tutorial de instalação [daqui](https://www.wireshark.org/docs/wsug_html_chunked/ChBuildInstallUnixInstallBins.html).\
Depois de instalado, você deve instalar o Plugin para conseguir ver a comunicação MAVLink entre a GCS e o drone. [Tutorial de instalação do Plugin](https://mavlink.io/en/guide/wireshark.html). \
Caso não tenha uma pasta em `~/.local/lib/wireshark/plugins`, você deve criá-la e copiar o Plugin para lá. <br/>
É previsto um erro ao abrir o Wireshark depois de instalar o Plugin: \
<img width="497" height="261" alt="image" src="https://github.com/user-attachments/assets/3c31abe4-3a4c-4fad-939e-c24142658cdd" />\
Para resolver esse problema, abra o `mavlink_2_common.lua` com algum editor de texto e na linha 6754 mude `base.HEX_DEC` para `base.DEC`: \
<img width="879" height="84" alt="image" src="https://github.com/user-attachments/assets/b573f821-030d-47be-a416-8e1863f4a301" />

### Se tudo der certo, você vai conseguir ver a troca de informações MAVLink entre a GCS e o drone:
<img width="1600" height="674" alt="image" src="https://github.com/user-attachments/assets/747e2341-0137-4150-979a-4be4aab4d0b4" />






