<div align="center">

<img width="100%" src="readme-assets/rq-medieval-banner.svg" alt="Banner medieval animado original para o projeto RQ-1.5"/>

<p>
  <img src="https://readme-typing-svg.demolab.com?font=Cinzel&weight=700&size=16&pause=1000&color=C49A45&center=true&vCenter=true&repeat=true&width=850&height=60&lines=Royal+Quest%3A+mapas%2C+miss%C3%B5es+e+mundos;Mobs+e+itens+do+cliente+em+pesquisa;RQ-1.5%3A+preserva%C3%A7%C3%A3o+e+emula%C3%A7%C3%A3o+experimental" alt="Mapas, missões, mobs e pesquisa sobre Royal Quest"/>
</p>

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

O **RQ-1.5** é um ambiente experimental para estudar e preservar aspectos técnicos do MMORPG **Royal Quest**. O repositório reúne um emulador de servidor ainda em desenvolvimento, ferramentas de observação de tráfego e utilitários para investigar arquivos e recursos do jogo.

O emulador é uma prova de conceito: algumas funções básicas já estão disponíveis, mas ele **não é um servidor completo** e pode não funcionar com todas as versões do cliente.

## O que existe aqui

- **Emulador `rqsrv`:** servidor experimental em Rust, acessível pelo cliente por meio de um proxy SOCKS5 local.
- **Modo de inspeção (`mitm`):** ferramenta para observar e analisar tráfego em ambientes de teste autorizados.
- **Comandos de teste no jogo:** trocar de local, invocar e mover mobs e adicionar itens.
- **Ferramentas auxiliares:** scripts PowerShell e Rust para investigar tabelas, localizações, modelos, mobs e outros recursos.
- **Cliente e recursos de teste:** organizados em `rqsrv_fresh/game-client`.

## Estrutura

| Caminho | Conteúdo |
|---|---|
| `rqsrv_fresh/source/rqrev-master/` | Código-fonte Rust do `rqsrv`, protocolo e emulador |
| `rqsrv_fresh/game-client/` | Cliente e recursos usados no ambiente local |
| `rqsrv_fresh/proxy/` | Proxychains e configuração para Windows |
| `rqsrv_fresh/GUIA_MOBS.md` | Notas sobre mobs, modelos e animações |
| Arquivos `*.ps1` e `*.rs` na raiz | Utilitários de investigação e inspeção de recursos |

## Requisitos

- Windows (os scripts `.bat` incluídos foram preparados para este ambiente).
- Rust com suporte à edição 2024 e toolchain **nightly** para o recurso experimental usado pelo código.
- Um cliente de Royal Quest compatível e obtido de forma autorizada para os testes locais.

## Compilar

No PowerShell, na raiz do repositório:

```powershell
cd .\rqsrv_fresh\source\rqrev-master
cargo +nightly build --release
```

O executável será gerado em `target\release\rqsrv.exe`.

## Executar

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

Os comandos são enviados pelo chat do jogo:

| Comando | Ação |
|---|---|
| `/loc <id>` | Solicita a troca para o local informado |
| `/spawnmob <id> [hp] [x] [y]` | Invoca um mob; `hp` é opcional e as coordenadas padrão são `0, 0` |
| `/movemob <id> <x> <y>` | Move uma entidade para as coordenadas indicadas |
| `/give <id> <quantidade>` | Adiciona uma quantidade de um item para teste |

## Aviso

Projeto independente, experimental e **não afiliado aos criadores ou operadores de Royal Quest**. Use somente clientes, servidores e tráfego para os quais você tenha autorização. O projeto é voltado a estudo e preservação; não use para bots, trapaças, exploração de serviços de terceiros ou violação dos termos do jogo.

Os componentes incluídos podem ter licenças diferentes. Consulte os arquivos de licença e avisos de cada componente antes de redistribuí-los.
