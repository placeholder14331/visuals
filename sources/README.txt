Combat Warriors - sistemas de cosmetico
=======================================

Fonte dos quatro sistemas de cosmetico do Combat Warriors (place 4282985734),
extraida do cliente em 2026-10-05. Os modulos sao do Combat Warriors; isto e
uma copia de leitura, publicada como referencia.

  Shared/Enchant          enchants de arma      107 modulos
  Shared/CharacterAura    auras de personagem   124
  Shared/KillEffect       kill effects           98
  Shared/Skin             skins de arma         129
  Shared/{Thing,Cosmetic,VFX,Scale,Number,Sound,Ragdoll,CollectionService}
                          utils usados pelos acima              30
  Client/*                handlers do lado cliente              10

Como os quatro sistemas funcionam
---------------------------------
Todos tem a mesma forma: <X>sMetadata monta a lista de configs via
ThingUtil.insertConfigs, e cada entrada tem rarity e um campo `apply` que e uma
funcao. Os visuais ficam separados, em ReplicatedStorage.Shared.Assets.Cosmetics.

Raridades: default < uncommon < rare < epic < legendary < exotic

Enchants e skins vem de fabricas de familia: 92 enchants saem de 10 creators, e
o config individual tem 4 linhas. Kill effects sao o oposto - 90 configs para 3
creators, ou seja quase todo efeito tem a coreografia escrita no proprio modulo.

Sobre estes arquivos
--------------------
Extensao .txt para leitura no navegador; o conteudo e Luau, e todos os 498
compilam (verificado com luau-compile).

Os identificadores gerados automaticamente pela extracao (p1, v8, t1) foram
renomeados a partir de como cada um e usado no proprio arquivo: um parametro
indexado com .HumanoidRootPart virou `character`, um valor testado com
:IsA("ParticleEmitter") virou `visual`, e assim por diante. Isso so foi feito
onde havia evidencia no codigo - onde nao havia, o nome original ficou, porque
um nome errado engana mais que um nome feio.

Os 458 arquivos de cosmetico estao quase todos sem nomes de maquina. Os 40 utils
genericos (VFX, Scale, Number, Ragdoll, Thing, Cosmetic, Sound e os handlers de
Client) ainda carregam, porque ali nao da para inferir intencao.

Caminhos, nomes de efeito e a API dos modulos foram mantidos intactos: sao
funcionais, e mexer neles quebraria o codigo.

_index.txt   caminho real no Roblox -> arquivo aqui
_summary.txt numeros da extracao
