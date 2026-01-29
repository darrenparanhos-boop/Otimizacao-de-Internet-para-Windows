# Otimizacao-de-Internet-para-Windows
O arquivo contém um script de otimização avançada de internet para sistemas Windows,com comandos PowerShell.

🛠 Otimização Avançada de Internet para Windows
Este script em PowerShell foi desenvolvido para realizar uma otimização avançada da conexão de internet em sistemas operacionais Windows. Ele executa uma série de comandos que ajudam a limpar configurações de rede antigas, renovar IPs e aplicar ajustes avançados no protocolo TCP, melhorando a performance e estabilidade da conexão.
📋 Funcionalidades
O script está dividido em duas seções principais:
1. Limpeza e Reset Básico
Realiza uma limpeza nas configurações de rede e renova os parâmetros de IP:
- ipconfig /flushdns: Limpa o cache DNS.
- ipconfig /release e ipconfig /renew: Libera e renova o endereço IP.
- arp -d *: Remove entradas da tabela ARP.
- netsh winsock reset: Reseta o catálogo Winsock.
- netsh int ip reset: Reseta a pilha TCP/IP.
2. Ajustes TCP Avançados
Aplica configurações que podem melhorar o desempenho da rede:
- autotuninglevel=normal: Ajusta o nível de autoajuste de recepção.
- rss=enabled: Ativa o Receive Side Scaling.
- rsc=enabled: Ativa o Receive Segment Coalescing.
- chimney=enabled: Ativa o offload de rede.
- ecncapability=disabled: Desativa o ECN (Explicit Congestion Notification).
- timestamps=disabled: Desativa timestamps TCP.
- congestionprovider=ctcp: Define o provedor de congestionamento como CTCP (Compound TCP).
⚠️ Requisitos
- Sistema operacional: Windows 10 ou superior.
- Permissões de administrador para executar os comandos netsh.
🚀 Como usar
- Abra o PowerShell como administrador.
- Copie e cole o conteúdo do arquivo .txt gerado.
- Pressione Enter para executar o script.
📌 Observações
- Este script não substitui uma análise técnica de rede, mas pode ajudar a resolver problemas comuns de lentidão ou instabilidade.
- Recomenda-se reiniciar o computador após a execução para aplicar todas as mudanças.

## 🔗 Link
[LinkedIn - Gabriel Otávio Rampon Fiamoncini](https://www.linkedin.com/posts/gabriel-ot%C3%A1vio-rampon-fiamoncini-031033293_script-avan%C3%A7ado-de-otimiza%C3%A7%C3%A3o-de-internet-activity-7420844800892981248-vBkK?utm_source=share&utm_medium=member_desktop&rcm=ACoAABkrG1QBn9zY1e1KmpXf0cLhpIFCTXG3T2A)

## 📄 Arquivo .txt
O script completo está disponível no arquivo: **otimizacao_internet.txt**  
*(Clique no cartão acima para baixar o arquivo gerado)*


[otimizacao_internet.txt](https://github.com/user-attachments/files/24943557/otimizacao_internet.txt)
Write-Host "==============================================" -ForegroundColor Cyan
Write-Host " OTIMIZACAO AVANCADA DE INTERNET - WINDOWS"
Write-Host "==============================================" -ForegroundColor Cyan

# -----------------------------------------------
# 1. Limpeza e reset basico
# -----------------------------------------------
Write-Host "`n[LIMPEZA DE REDE]" -ForegroundColor Yellow
ipconfig /flushdns
ipconfig /release
ipconfig /renew
arp -d *

netsh winsock reset
netsh int ip reset

# -----------------------------------------------
# 2. Ajustes TCP Avancados
# -----------------------------------------------
Write-Host "`n[AJUSTES TCP]" -ForegroundColor Yellow

netsh int tcp set global autotuninglevel=normal
netsh int tcp set global rss=enabled
netsh int tcp set global rsc=enabled
netsh int tcp set global chimney=enabled
netsh int tcp set global ecncapability=disabled
netsh int tcp set global timestamps=disabled
netsh int tcp set global congestionprovider=ctcp
