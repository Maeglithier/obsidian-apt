# Repositório APT Não-Oficial obsidian

Repositório APT Não-Oficial do [obsidian](https://github.com/adlerosn/obsidian).

Use este repositório para instalar e atualizar o pacote obsidian com facilidade usando o APT.

Antes de confiar neste repositório, verifique a integridade dos arquivos e considere sua segurança primeiro. Crie seu próprio repositório APT usando este como base ou utilize o meu que buscará atualizações diariamente.

## Requisitos

- Debian/Ubunto ou qualquer distro derivado destes.

## Como instalar o repositório APT

Para que o APT identifique este repositório e seja capaz de instalar e atualizar o Discord você deve executar os códigos abaixo.

```shell
sudo apt remove obsidian # Apenas se você instalou o obsidian usando o arquivo deb. Neste caso, desinstale primeiro.
wget -qO- https://maeglithier.github.io/obsidian-apt/pubkey.asc | sudo gpg --dearmor -o /usr/share/keyrings/obsidian-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/obsidian-archive-keyring.gpg] https://maeglithier.github.io/obsidian-apt stable main" | sudo tee /etc/apt/sources.list.d/obsidian.list >/dev/null
sudo apt update
sudo apt install obsidian -y # Agora você está pronto para instalar e atualizar sempre que uma nova versão lançar.
```

## Como faço para desinstalar este repositório?

Para remover este repositório e sua chave pública você deve executar os códigos abaixo.

```shell
sudo apt remove obsidian # Apenas se você ainda não desinstalou o obsidian. Neste caso, desinstale primeiro.
sudo rm /usr/share/keyrings/obsidian-archive-keyring.gpg
sudo rm /etc/apt/sources.list.d/obsidian.list
```

## Checksum

772da38d23b15f0f5d7cf17024a1948ff2c073b2195954743703178bf1254b36  pool/main/o/obsidian/obsidian_1.6.7_amd64.deb

## Copyright

O instalador do obsidian (arquivos deb) são distribuidos sob sua prórpia [licença](https://obsidian.md/license), [Termo de serviço](https://obsidian.md/terms) e de [privacidade](https://obsidian.md/privacy) ou qualquer outro termo ou licença usada pelo Obsidian.

Declaro que não tomo autoria pelos arquivos deb presentes na pasta pool e que este repositório possui a unica e exclusiva finalidade de distribuir estes arquivos de forma tal que um usuário qualquer possa instalar e atualizar o obsidian usando o APT. Com isso quero dizer que o repositório irá baixar a ultima versão disponivel desses arquivos e deixar disponivel neste repositório.

Declaro também que a licensa existente neste repositório não se aplica a nenhum arquivo da pasta pool, visto que os arquivos deb pertecem ao obsidian.
