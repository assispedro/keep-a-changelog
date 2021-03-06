# Mantenha um CHANGELOG

## Não deixe seus amigos despejar logs de commits em CHANGELOGs™

### O que é um *change log*?
Um *change log* é um arquivo que contém uma lista selecionada, ordenada cronologicamente de mudanças significativas para cada versão de um projeto open source.

<a href="CHANGELOG.md" title="An example of a CHANGELOG file."><iframe src="CHANGELOG.md" width="570" height="350" seamless="seamless" style="border: 1px solid #aaa; padding: 1em; margin: 0 0.5em;"></iframe></a>

### Para que serve um *change log*?
Para facilitar para os usuários e contribuidores verem precisamente quais mudanças significativas foram realizadas entre cada versão publicada.

### Por quê eu deveria me importar?
Porque softwares são feitos para pessoas. Se você não liga, porque está contribuindo a projetos open source? Certamente deve haver um fundo de carinho em algum lugar dessa sua cabeçinha.

Eu [conversei com Adam Stacoviak e Jerod Santo no podcast do The Changelog][thechangelog] (faz sentido, hein?) sobre o por quê mantenedores e contribuidores open source devem se importar, e as motivações por trás deste projeto.
Se você tem o tempo (1:06), é um bom programa.

### O que faz um *change log* ser bom?
Que bom que perguntou.

Um bom *change log* não foge desses princípios:

- É feito para seres humanos, não máquinas, então legibilidade é crucial.
- Ser fácil de referenciar (*linkar*) qualquer seção (por isso Markdown ao invés de puro texto).
- Uma sub-seção por versão.
- Lista as versões publicadas em ordem cronológica decrescente (mais novo em cima).
- Escreva todas as datas no formato `AAAA-MM-DD`. (Exemplo: `2012-06-02` para `2 de Junho de 2012`.) É internacional, [sensato](http://xkcd.com/1179/), e independente de língua.
- Explicite se o projeto segue [Versionamento Semântico][semver].
- Cada versão deve:
  - Listar sua data de publicação no formato acima.
  - Agrupar mudanças descrevendo seus impactos no projeto, como segue:
    - `Adicionado` para novas funcionalidades.
    - `Modificado` para mudanças em funcionalidades existentes.
    - `Obsoleto` para funcionalidades uma vez estáveis removidas das próximas publicações.
    - `Removido` para funcionalidades removidas desta versão.
    - `Corrigido` para qualquer correção de bug.
    - `Segurança` para convidar usuários a atualizar em caso de vulnerabilidades.

### Como eu posso minimizar o esforço exigido?
Mantenha sempre uma seção `Não publicado` no topo para manter o controle de quaisquer mudanças.

Isso serve a dois propósitos:

- As pessoas podem ver quais mudanças elas podem esperar em publicações futuras.
- No momento da publicação, você tem que somente mudar `Não publicado` para o número de versão e adicionar um novo cabeçalho `Não publicado` no topo.

### O que faz os unicórnios chorarem?
Tudo bem...vamos lá.

- **Despejar logs de commits.** Simplesmente não faça isso, você não está ajudando ninguém.
- **Não dar ênfase nas descontinuações.** Quando as pessoas atualizam de uma versão para outra, deve ser incrivelmente claro quando algo irá quebrar.
- **Datas em formatos específicos de uma região.** Nos Estados Unidos, as pessoas colocam o mês primeiro ("06-02-2012" para 2 de Junho de 2012, o que *não* faz sentido), enquanto muitos no resto do mundo escrevem em aspecto robótico "2 Junho 2012", e mesmo assim leem de forma diferente. "2012-06-02" funciona de maneira lógica do maior para o menor, não sobrescreve de maneira ambígua outros formatos, e é um [padrão ISO](http://www.iso.org/iso/home/standards/iso8601.htm). Portanto, é o formato recomendado para *change logs*.

Tem mais. Ajude me a coletar essas lágrimas de unicórnio [abrindo uma issue][issues] ou um pull request.

### Existe um padrão de formato de *change log*?
Infelizmente, não. Calma. Eu sei que você está indo impetuosamente achar aquele link do guia de estilo de *change log* GNU, ou o arquivo "guideline" de dois paragráfos GNU NEWS. O estilo GNU é um bom começo mas é ingênuo. Não há nada de errado em ser ingênuo mas quando as pessoas precisam de orientação raramente ajuda. Especialmente quando existem muitas situações excepcionais para lidar.

Este projeto [contém o que eu espero se tornar um melhor padrão de arquivo CHANGELOG][CHANGELOG] para todos projetos open source. Pode a comunidade open source aprender com seus erros e não agir como se os dez mandamentos foram escritos a muito tempo atrás e estavam inteiramente certos? Tudo bem. Então por favor dê um olhada e lembre que [discussões e sugestões de melhorias são bem-vindas][issues]!

### Qual deve ser o nome do arquivo *change log*?
Bom, se você não notou no exemplo acima, `CHANGELOG.md` é a melhor padrão até agora.

Alguns outros projetos também utilizam `HISTORY.txt`, `HISTORY.md`, `History.md`, `NEWS.txt`, `NEWS.md`, `News.txt`, `RELEASES.txt`, `RELEASE.md`, `releases.md`, etc.

É uma bagunça. Todos esses nome só dificultam as pessoas acharem.

### Por quê as pessoas não podem simplesmente utilizar `git log`?
Porque logs de commit são cheios de distrações. Podemos realmente esperar que cada commit do projeto seja significativo e auto-explicativo? Só em sonho.

### Podem os *change logs* ser automaticamente interpretados?
É difícil, por que as pessoas seguem formatos e nomes de arquivos radicalmente diferentes.

[Vandamme][vandamme] é uma gem criada pelo time [Gemnasium][gemnasium] que interpreta muitos (mas não todos) *change logs* de projetos open source.

### Por que você alterna entre as grafias "CHANGELOG" e "change log"?
"CHANGELOG" é o nome do arquivo em si. É um pouco chamativo mas é uma convenção histórica seguida por muitos projetos open source. Outros exemplos similares de arquivo incluem [`README`](README.md), [`LICENSE`](LICENSE), e [`CONTRIBUTING`](CONTRIBUTING.md).

O nome em letras maiúsculas (o que em sistemas operacionais antigos faziam estes arquivos serem mantidos no topo) é utilizado para chamar atenção a eles. Já que eles são importante metadados sobre o projeto, eles podem ser úteis a qualquer um pretendendo usar ou contribuir com ele, assim como os [as *badges* de projeto open source][shields].

Quando eu me refiro a "*change log*", eu estou falando sobre a função deste arquivo: listar mudanças.

### E sobre as publicações removidas?
Publicações removidas são versões que tiveram que ser removidas devido a um sério bug ou problema de segurança. Com frequência essas versões sequer aparecem em *change logs*. Deveriam. É assim que você deve exibi-las:

`## 0.0.5 - 2014-12-13 [REMOVIDO]`

A tag `[REMOVIDO]` é chamativa por uma razão. É importante que as pessoas a notem. E já que é cercada por colchetes é mais fácil detectá-la programaticamente.

### Como eu posso contribuir?
Este documento não é **a verdade**; é minha cuidadosa opinião, junto com as informações e exemplos que reuni. Embora eu tenha providenciado um [CHANGELOG][] no [repositório no GitHub][gh], eu não criei de propósito uma lista clara de regras a serem seguidas (como o [SemVer.org][semver] faz, por exemplo).

Fiz isso porque eu gostaria que nossa comunidade chegasse a um consenso. Eu acredito que a discussão é tão importante quanto o resultado final.

Então por favor [**entre em campo**][gh].

### Isto é uma tradução

*[Tradutor](https://github.com/tallesl) falando*.

Isto é uma tradução de [keepachangelog.com][doc-original].

Para contribuir com a discussão e a formulação do documento utilize o [repositório original][repo-original]. Para contribuir com a tradução utilize [este fork][repo-fork].

[CHANGELOG]: ./CHANGELOG.md
[gemnasium]: http://gemnasium.com
[gh]: https://github.com/olivierlacan/keep-a-changelog
[issues]: https://github.com/olivierlacan/keep-a-changelog/issues
[semver]: http://semver.org
[shields]: http://shields.io
[thechangelog]: http://5by5.tv/changelog/127
[vandamme]: https://github.com/tech-angels/vandamme/

[doc-original]: http://keepachangelog.com/
[repo-original]: https://github.com/olivierlacan/keep-a-changelog
[repo-fork]:  https://github.com/tallesl/keep-a-changelog
