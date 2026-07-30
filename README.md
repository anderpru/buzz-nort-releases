# Buzz Nort — instaladores

Instaladores e manifesto de atualização do **Buzz Nort**, o fork interno da Nort
do [block/buzz](https://github.com/block/buzz). O código-fonte fica no
repositório privado `anderpru/buzz-nort`; aqui ficam só os binários, porque o
atualizador automático do app precisa de URLs públicas para baixar as versões.

## Instalar

Baixe o instalador da versão mais recente em
[Releases](https://github.com/anderpru/buzz-nort-releases/releases/latest):

| Sistema | Arquivo |
|---|---|
| Windows 10/11 | `Buzz_<versão>_x64-setup.exe` |
| macOS (Apple Silicon) | `Buzz_<versão>_aarch64.dmg` |

Os instaladores não têm certificado de fabricante, então o sistema mostra um
aviso na primeira instalação:

- **Windows** — o SmartScreen diz "Windows protegeu seu PC". Clique em
  *Mais informações* → *Executar assim mesmo*.
- **macOS** — o Gatekeeper bloqueia o app baixado. Rode uma vez no Terminal:
  `xattr -dr com.apple.quarantine /Applications/Buzz.app`

Depois da primeira instalação o app se atualiza sozinho e esses avisos não
voltam a aparecer.

## Atualização automática

O app consulta `latest.json` da tag `latest` a cada 6 horas e no início de cada
sessão, baixa a nova versão em segundo plano e oferece reiniciar. Os pacotes são
assinados com a chave de atualização da Nort — o app recusa qualquer pacote que
não tenha essa assinatura.