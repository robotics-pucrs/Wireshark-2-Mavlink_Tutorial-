# Wireshark-2-Mavlink_Tutorial
Tutorial completo de instalação das ferramentas necessárias para visualizar a comunição Mavlink entre Ground Control Station e Drone.

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
Coloque o nome que você preferir, mude Type para UDP e coloque o IPv4 do drone seguido da porta(14550)\
<img width="442" height="392" alt="image" src="https://github.com/user-attachments/assets/ab9d9fa7-a54f-46eb-9b03-0b6edc05d78e" />\




## Instalando Wireshark

Seguir tutorial de instalação [daqui](https://www.wireshark.org/docs/wsug_html_chunked/ChBuildInstallUnixInstallBins.html).\
Depois de instalado, você deve instalar o Plugin para conseguir ver a comunicação MAVLink entre a GCS e o drone. [Tutorial de instalação do Plugin](https://mavlink.io/en/guide/wireshark.html). \
Caso não tenha uma pasta em ~/.local/lib/wireshark/plugins, você deve criá-la e copiar o Plugin para lá. \ 
É previsto um erro ao abrir o Wireshark depois de instalar o Plugin\
<img width="497" height="261" alt="image" src="https://github.com/user-attachments/assets/3c31abe4-3a4c-4fad-939e-c24142658cdd" />\
Para resolver esse problema, abra o mavlink_2_common.lua com algum editor de texto e na linha 6754 mude base.HEX_DEC para base.DEC: \
<img width="879" height="84" alt="image" src="https://github.com/user-attachments/assets/b573f821-030d-47be-a416-8e1863f4a301" />\





