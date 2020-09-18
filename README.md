# Compartilhamento de arquivos via protocolo `torrent`

## Compartilhamento de arquivos através no protocolo torrent e links magnet

## 1- Instalação

### Linux - instalando as dependências no usuário local

Arrume a variável de ambiente PATH para que ela também procure no
diretório de pacotes python do usuário local

```bash
export PATH="$(python3 -m site --user-base)/bin:${PATH}"
```
Instale dependências
```bash
pip3 install --user --upgrade pyxdg torf 
```
instale a ferramenta
```bash
pip3 install --user --upgrade   git+https://github.com/rndusr/torf-cli.git
```
# 2- Geração do torrent a partir do arquivo

Vou gerar um apontamento `.torrent`.
Por exemplo, o arquivo Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4 ser compartilhado através de um "atalho" chamado _Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4.torrent

```bash
torf ./Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4 \
-t udp://tracker_proxy:56/announce \
-t udp://tracker_proxy:57/announce \
-t udp://tracker_proxy:58/announce \
-t udp://tracker_proxy:59/announce \
-t udp://tracker_proxy:60/announce \
-t udp://tracker_proxy:61/announce \
-t udp://tracker_proxy:62/announce \
-t udp://tracker_proxy:63/announce \
-t udp://tracker_proxy:64/announce \
-t udp://tracker_proxy:65/announce \
-t udp://tracker_proxy:66/announce \
-t udp://tracker_proxy:67/announce \
-t udp://tracker_proxy:68/announce \
-t https://tracker.bt-hash.com:443/announce \
-t udp://tracker.leechers-paradise.org:6969 \
-t https://182.176.139.129:6969/announce \
-t udp://zephir.monocul.us:6969/announce \
-t https://tracker.dutchtracking.com:80/announce \
-t https://grifon.info:80/announce \
-t udp://tracker.kicks-ass.net:80/announce \
-t udp://p4p.arenabg.com:1337/announce \
-t udp://tracker.aletorrenty.pl:2710/announce \
-t udp://tracker.sktorrent.net:6969/announce \
-t udp://tracker.internetwarriors.net:1337/announce \
-t https://tracker.parrotsec.org:443/announce \
-t https://tracker.moxing.party:6969/announce \
-t https://tracker.ipv6tracker.ru:80/announce \
-t https://tracker.fastdownload.xyz:443/announce \
-t udp://open.stealth.si:80/announce \
-t https://gwp2-v19.rinet.ru:80/announce \
-t https://tr.kxmp.cf:80/announce \
-t https://explodie.org:6969/announce \
--private --date '2020-09-18 22:00:00' \
-o _Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4.torrent
```
Pronto, agora você tem o arquivo \_Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4.torrent para enviar para alguém que queira copiar
o seu arquivo Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4 direto de sua máquina.

# 3- Adicionando um comentário

```bash
torf -i _Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4.torrent \
 --comment 'Meu dataset' \
 -o Geospatial_Queries_using_Apache_Spark_GeoSpark_and_Hadoop.mp4.torrent
```

Ligue seu cliente torrent preferido para que o arquivo possa ser semeado/baixado
a outros solicitantes ao menos 1 vez.
