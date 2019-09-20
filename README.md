enable
configure terminal
hostname SW-02
banner motd "ACESSO AUTORIZADO APENAS PARA O DEPARTAMENTO DE TI!"
enable secret SenhaEnable
ip domain-name peachanddaisy.local
crypto key generate rsa general-keys modulus 1024
username administrador privilege 15 secret SenhaAdmin
username estagiario privilege 1 secret SenhaEst
line console 0
password SenhadaConsole
login
exit
service password-encryption
line vty 0 15
password SenhadaVTY
transport input ssh
login local
exit
exec-timeout 5
