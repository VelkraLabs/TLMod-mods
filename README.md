# TLMod-mods

Os mods da equipe do TLMod para o **Baixar Mods** da Oficina de Mods (o carregador de mods do Terraria Mobile).
Este repositório tem só mods prontos: nenhum código do TLMod e nenhum arquivo do jogo.

| arquivo | o quê |
|---|---|
| `catalog.json` | a lista dos mods: id, nome, versão, autores, descrição e, por plataforma, o endereço, o tamanho e o SHA-256 do pacote |
| `catalog.json.sig` | a assinatura Ed25519 do `catalog.json`, em hex |
| `pacotes/` | os pacotes (zip) dos mods |

O TLMod só lê o catálogo se a assinatura bater com uma das chaves que ele traz, e só instala um pacote com o
tamanho e o SHA-256 do catálogo. O catálogo e os pacotes são gerados pelo `tools/publicar_mods.py` do TLMod.

## O catálogo

O catálogo é assinado pela **chave da equipe** (`e8c9f732…2824e06`), que toda build do TLMod aceita. Ele traz 9
mods: Armament Display, Basic Automated Mining, Boss Checklist, Expanded Inventory, Loot Beams, No More Tombs,
Overhealth, Shorter Respawn e Visual Tweaks. Os pacotes ficam na pasta `pacotes/`.

Para publicar uma versão nova, quem guarda a chave privada roda o `tools/publicar_mods.py catalogo` do TLMod com
a pasta dos mods e troca aqui o `catalog.json`, o `catalog.json.sig` e os zips.
