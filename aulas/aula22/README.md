Serviço Nacional de Aprendizagem Comercial  
Brasília, 7 de outubro de 2025  
Anderson de Matos Guimarães  
Professor: Moisés Mendes de Andrade

# MÁSCARAS DE RESDES VLSM (VARIABLE LENGTH SUBNET MASK)

Máscara de sub-rede de comprimento variável é uma técnica de sub-rede que permite que os administradores de rede aloquem endereços IP de forma mais eficiente usando diferentes máscaras de sub-rede.  
Ele fornece maior flexibilidade na atribuição de endereços IP, criando sub-redes de tamanhos variados com base nas necessidades específicas e número de hosts em cada sub-rede.

## Metodologia de cálculo
1. ordem de tamanho
2. .
3. .
4. .

## Exemplo prático 1:  ordenar e alocar

Rede 192.168.10.0/24  
Requisitos: a empresa precisa de 2, 10 e 50 hosts

|$2^7$ |$2^6$ | $2^5$ | $2^4$ | $2^3$ | $2^2$ | $2^1$ | $2^0$ |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1|

Tabela de Prioridade:
| Requisitos | Hosts necessários | cálculo ($2^n$)| Prefixo (máscara)| 
| --- | :---: | --- | --- |
| 1º maior | 50 | $2^6 = 64$| $256 - 64 = 192$ => 2255.255.255.192/26 |
| 2º maior | 10| $2^4 = 16$ | $256 - 16 = 240$ => 255.255.255.240/28 |
| 3º maior | 2 | $2^2 = 4$ | $256 - 4 = 252$ => 255.255.255.252/30|

| Requisito | Máscara CIDR | Endereço de rede| Intervalo de hosts| Endereço de broadcast|
| --- | --- | --- | --- | --- |
| 50 hosts | /26 | 192.168.10.0 | 192.168.10.1 a 192.168.10.62 | 192.168.10.63 |
| 10 hosts | /28 | 192.168.10.64 | 192.168.10.65 a 192.168.10.78 | 192.168.10.79 |
| 2 hosts | /30 | 192.1268.10.80 | 192.168.10.81 a 192.168.10.2 | 192.168.10.83 |

---
