<div align="center">

<img width="100%" src="readme-assets/rq-medieval-banner-v3.svg" alt="Banner medieval animado original para o projeto RQ 1.5"/>

<p>
  <img height="38" src="readme-assets/royal-quest-map.png" alt="Ícone do mapa global de Royal Quest"/>
  &nbsp;
  <img height="38" src="readme-assets/royal-quest-story.png" alt="Ícone de missão da história de Royal Quest"/>
  &nbsp;
  <img height="38" src="readme-assets/royal-item.png" alt="Ícone de item Royal do jogo"/>
</p>

<p>
  <img src="https://img.shields.io/badge/status-experimental-C49A45?style=for-the-badge&labelColor=29231D" alt="Status experimental"/>
  <img src="https://img.shields.io/badge/Rust-2024-9A5A36?style=for-the-badge&logo=rust&logoColor=F3E6C8&labelColor=29231D" alt="Rust 2024"/>
  <img src="https://img.shields.io/badge/plataforma-Windows-426B59?style=for-the-badge&logo=windows&logoColor=F3E6C8&labelColor=29231D" alt="Windows"/>
</p>

</div>

---

## Sobre o projeto

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C1&width=1000&height=72&letterSpacing=1&lines=Um+ambiente+experimental+para+estudar+e+preservar+Royal+Quest;Emulador+e+ferramentas+de+pesquisa+em+desenvolvimento;Prova+de+conceito%3A+n%C3%A3o+%C3%A9+um+servidor+completo" alt="Ambiente experimental para estudar e preservar Royal Quest, com emulador e ferramentas de pesquisa em desenvolvimento; não é um servidor completo."/></p>

O **RQ 1.5** é um ambiente experimental para estudar e preservar aspectos técnicos do MMORPG **Royal Quest**. O repositório reúne um emulador de servidor ainda em desenvolvimento, ferramentas de observação de tráfego e utilitários para investigar arquivos e recursos do jogo.

O emulador é uma prova de conceito: algumas funções básicas já estão disponíveis, mas ele **não é um servidor completo** e pode não funcionar com todas as versões do cliente.

## O que existe aqui

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C3&width=1000&height=72&letterSpacing=1&lines=Emulador+Rust+com+proxy+SOCKS5;Inspe%C3%A7%C3%A3o+de+tr%C3%A1fego+em+ambientes+autorizados;Comandos+de+teste+para+locais%2C+mobs+e+itens;Ferramentas+de+pesquisa+do+cliente+e+seus+recursos;Cliente+local+em+rqsrv_fresh%2Fgame-client" alt="Emulador Rust com proxy SOCKS5, inspeção autorizada, comandos de teste e ferramentas de pesquisa do cliente."/></p>

- **Emulador `rqsrv`:** servidor experimental em Rust, acessível pelo cliente por meio de um proxy SOCKS5 local.
- **Modo de inspeção (`mitm`):** ferramenta para observar e analisar tráfego em ambientes de teste autorizados.
- **Comandos de teste no jogo:** trocar de local, invocar e mover mobs e adicionar itens.
- **Ferramentas auxiliares:** scripts PowerShell e Rust para investigar tabelas, localizações, modelos, mobs e outros recursos.
- **Cliente e recursos de teste:** organizados em `rqsrv_fresh/game-client`.

## Estrutura

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C3&width=1000&height=72&letterSpacing=1&lines=rqrev-master%3A+protocolo+e+emulador;game-client%3A+cliente+e+recursos;proxy%3A+Proxychains+para+Windows;GUIA_MOBS.md%3A+notas+sobre+mobs+e+anima%C3%A7%C3%B5es;Scripts+PowerShell+e+Rust%3A+pesquisa+de+recursos" alt="Pastas do emulador, cliente, proxy, guia de mobs e ferramentas de pesquisa."/></p>

| Caminho | Conteúdo |
|---|---|
| `rqsrv_fresh/source/rqrev-master/` | Código-fonte Rust do `rqsrv`, protocolo e emulador |
| `rqsrv_fresh/game-client/` | Cliente e recursos usados no ambiente local |
| `rqsrv_fresh/proxy/` | Proxychains e configuração para Windows |
| `rqsrv_fresh/GUIA_MOBS.md` | Notas sobre mobs, modelos e animações |
| Arquivos `*.ps1` e `*.rs` na raiz | Utilitários de investigação e inspeção de recursos |

## Requisitos

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C1&width=1000&height=72&letterSpacing=1&lines=Windows+e+scripts+.bat+preparados+para+este+ambiente;Rust+2024+com+toolchain+nightly;Cliente+compat%C3%ADvel+e+obtido+de+forma+autorizada" alt="Windows, Rust 2024 com nightly e cliente compatível obtido de forma autorizada."/></p>

- Windows (os scripts `.bat` incluídos foram preparados para este ambiente).
- Rust com suporte à edição 2024 e toolchain **nightly** para o recurso experimental usado pelo código.
- Um cliente de Royal Quest compatível e obtido de forma autorizada para os testes locais.

## Compilar

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C1&width=1000&height=72&letterSpacing=1&lines=PowerShell%3A+acesse+a+pasta+rqrev-master;Cargo+%2Bnightly+build+%2D%2Drelease;Execut%C3%A1vel+em+target%5Crelease%5Crqsrv.exe" alt="Acesse rqrev-master no PowerShell e compile com cargo +nightly build --release."/></p>

No PowerShell, na raiz do repositório:

```powershell
cd .\rqsrv_fresh\source\rqrev-master
cargo +nightly build --release
```

O executável será gerado em `target\release\rqsrv.exe`.

## Executar

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C2&width=1000&height=72&letterSpacing=1&lines=rqsrv.exe+server%3A+iniciar+o+emulador;SOCKS5+local+em+127.0.0.1%3A8008;rqsrv.exe+mitm%3A+inspe%C3%A7%C3%A3o+autorizada;Ajuste+os+caminhos+absolutos+dos+scripts+.bat" alt="Inicie o emulador, conecte pelo SOCKS5 local ou use mitm apenas para inspeção autorizada."/></p>

Inicie o emulador local:

```powershell
.\target\release\rqsrv.exe server
```

Ele aceita conexões SOCKS5 em `127.0.0.1:8008`. Para iniciar o modo de inspeção de tráfego em um ambiente autorizado:

```powershell
.\target\release\rqsrv.exe mitm
```

Também existem scripts `.bat` em `rqsrv_fresh/` para iniciar o servidor, o modo de inspeção e o cliente. **Eles contêm caminhos absolutos da máquina de desenvolvimento**; ajuste os caminhos antes de usá-los em outro computador.

## Comandos de teste

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C2&width=1000&height=72&letterSpacing=1&lines=%2Floc+%3Cid%3E%3A+trocar+de+local;%2Fspawnmob+%3Cid%3E+%5Bhp%5D+%5Bx%5D+%5By%5D%3A+invocar+mob;%2Fmovemob+%3Cid%3E+%3Cx%3E+%3Cy%3E%3A+mover+entidade;%2Fgive+%3Cid%3E+%3Cquantidade%3E%3A+adicionar+item" alt="Comandos animados para trocar de local, invocar e mover mobs e adicionar itens."/></p>

Os comandos são enviados pelo chat do jogo:

| Comando | Ação |
|---|---|
| `/loc <id>` | Solicita a troca para o local informado |
| `/spawnmob <id> [hp] [x] [y]` | Invoca um mob; `hp` é opcional e as coordenadas padrão são `0, 0` |
| `/movemob <id> <x> <y>` | Move uma entidade para as coordenadas indicadas |
| `/give <id> <quantidade>` | Adiciona uma quantidade de um item para teste |

## Aviso

<p align="center"><img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&duration=3200&pause=850&color=C49A45&center=true&vCenter=true&repeat=true&multiline=true&groups=2%2C2&width=1000&height=72&letterSpacing=1&lines=Projeto+independente%2C+experimental+e+n%C3%A3o+afiliado;Use+somente+clientes%2C+servidores+e+tr%C3%A1fego+autorizados;N%C3%A3o+use+para+bots%2C+trapa%C3%A7as+ou+explora%C3%A7%C3%A3o+de+terceiros;Consulte+as+licen%C3%A7as+antes+de+redistribuir" alt="Projeto experimental independente; use apenas clientes, servidores e tráfego autorizados e consulte as licenças antes de redistribuir."/></p>

Projeto independente, experimental e **não afiliado aos criadores ou operadores de Royal Quest**. Use somente clientes, servidores e tráfego para os quais você tenha autorização. O projeto é voltado a estudo e preservação; não use para bots, trapaças, exploração de serviços de terceiros ou violação dos termos do jogo.

Os componentes incluídos podem ter licenças diferentes. Consulte os arquivos de licença e avisos de cada componente antes de redistribuí-los.
