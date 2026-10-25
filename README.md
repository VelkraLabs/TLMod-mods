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

## Catálogo de teste

**O catálogo atual é de teste**: assinado com a chave de teste, que só a build de teste do TLMod aceita (a build
normal ignora este catálogo). Ele traz os mods do pacote de teste 42 do TLMod; o `tlmod.example_boss` vai como
0.1.1 (só o `manifest.json` muda em relação ao 0.1.0 do pacote) para dar o que atualizar no teste.

Quando a equipe gerar a chave dela, o catálogo de verdade substitui este, e os pacotes passam para as Releases
do repositório.
