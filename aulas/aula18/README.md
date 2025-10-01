Serviço Nacional de Aprendizagem Comercial  
Brasília, 1º de outubro de 2025  
Anderson de Matos Guimarães  
Professor: Moisés Mendes de Andrade

# ATIVIDADES SUB-REDES

## Exemplo 1

Dada a rede 192.168.1.0/24, seu iobjetivo é **dividir essa rede em 8 sub-redes com o mesmo tamanho**.  
Você deve apresentar a solução seguindo os passos abaixo, para determinar as novas redes e a máscara correta.

| 128 | 64 | 32| 16 | 8 | 4 | 2 | 1 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 1 | 1 | 0 | 0 | 0 | 0 | 0| 

$$ 2^3 = 8  -> {total de sub-redes} $$
$$ 2^5 - 2 = 32 -2 = 30 $$

| Endereço IP | Máscara CIDR | Endereço de rede | Intervalo de hosts | Broadcast |
| :---: | :---:| :---: | :---: | :---: |
| 192.168.1.0/27 | 255.255.255.224 | 192.168.1.0 |  192.168.1.1 -> 192.168.1.30  | 192.168.1.31 |
