Serviço Nacional de Aprendizagem Comercial  
Brasília, 1º de outubro de 2025  
Anderson de Matos Guimarães  
Professor: Moisés Mendes de Andrade

# ATIVIDADES SUB-REDES

## Exercício 1

Dada a rede 192.168.1.0/24, seu objetivo é **dividir essa rede em 8 sub-redes com o mesmo tamanho**.  
Você deve apresentar a solução seguindo os passos abaixo, para determinar as novas redes e a máscara correta.

| 128 | 64 | 32| 16 | 8 | 4 | 2 | 1 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0 | 

$$
2^3 = 8 \text{ → total de sub-redes}
$$

$$
2^5 - 2 = 32 - 2 = 30 \text{ → total de hosts utilizáveis por sub-rede}
$$


| Endereço IP | Máscara CIDR | Endereço de rede | Intervalo de hosts | Broadcast |
| :---: | :---:| :---: | :---: | :---: |
| 192.168.1.0 | 255.255.255.224/27 | 192.168.1.0 |  192.168.1.1 -> 192.168.1.30  | 192.168.1.31 |
| 192.168.1.32 | 255.255.255.224/27 | 192.168.1.32 | 192.168.1.33 -> 192.168.1.62 | 192.168.1.63 |
| 192.168.1.64 | 255.255.255.224/27 | 192.168.1.64 | 192.168.1.65 -> 192.168.1.94 | 192.168.1.95 |
| 192.168.1.96 | 255.255.255.224/27 | 192.168.1.96 | 192.168.1.97 -> 192.168.1.126 | 192.168.1.127 |
| 192.168.1.128 | 255.255.255.224/27 | 192.168.1.128 | 192.168.1.129  -> 192.168.1.158 |192.168.1.159 |
| 192.168.1.160 | 255.255.255.224/27 | 192.168.1.160 | 192.168.1.161 > 192.168.1.190 | 192.168.1.191 |
| 192.168.1.192 | 255.255.255.224/27 | 192.168.1.192 | 192.168.1.193 -> 192.168.1.222 | 192.168.1.223 |
| 192.168.1.224 | 255.255.255.224/27 | 192.168.1.224 | 192.168.1.225 -> 192.168.1.254 | 192.168.1.255 |

## Exercício 2

| Endereço IP | Requisito | Máscara CIDR | Número de sub-redes | Endereço de rede | Broadcast |
| :--- | :---: | :---: | :---: | :--- | :--- | 
| 192.168.1.0/24 | Dividir em 4 sub-redes | | | | |
| 172.16.0.0/16| Dividir em 8 sub-redes| | | | | 
| 192.168.10.0/24| Dividir em 32 sub-redfes| | | | |
| 10.0.0.0/8 | Dividir em 4 sub-redes | | | | |
| 172.30.0.0/16| Dividir em 16 sub-redes | | | | |

---
### 192.168.1.0/24 em 4 sub-redes:  

$$2^x = 4 => 2^2 = 4 \quad \therefore \quad \text{números de bits ativados = 2}$$

| 128 | 64 | 32| 16 | 8 | 4 | 2 | 1 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 

**Nova máscara de rede:**

255.255.255.192/26

**Número de hosts por sub-rede:**

$$2^\text{(32-CIDR)} - 2 \quad \therefore \quad 2^\text{(32-26)} - 2 \quad \therefore \quad 2^6 - 2 \quad \therefore \quad 64 - 2 = 62 \quad \text{hosts úteis}$$

**Incremento**

$$ 256 - \text{(último valor da máscara)} \quad \therefore \quad 256 - 192 = 64 $$

| Endereço de rede | Intervalo de hosts | Endereço de broadcast |
| :--- | :--- | ---: |
| 192.168.1.0 | 192.168.1.1 -> 192.168.1.62 | 192.168.1.63 |
| 192.168.1.64 | 192.168.1.65 -> 192.168.1.126 | 192.168.1.127 |
| 192.168.1.128 | 192.168.1.129 -> 192.168.1.190| 192.168.1.191|
| 192.168.1.192 | 192.168.1.193 -> 192.168.1.254 | 192.168.1.255 |







