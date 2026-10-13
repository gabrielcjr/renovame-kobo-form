# Formulário: Missionários Renova-me (KoBoToolbox / OpenRosa)

Repositório com a definição completa, formato XLSForm, especificação XForm XML e mídias do formulário **Missionários Renova-me** da Igreja Renova-me.

---

## 📋 Informações do Formulário

- **Título:** Missionários Renova-me
- **Form ID:** `a7FqboN3tiXKPo6hSc8MzJ`
- **Versão:** `32 (2025-09-12 17:50:03)`
- **UUID Original:** `fe67ba249d41444a9de6eea1f809669d`
- **Link Enketo Original:** `https://ee.kobotoolbox.org/x/PY2hbkKi`
- **Novo Servidor Local (K3s):** `https://kobo.gabrielcjr.website` (ou `https://kobo.gabriel.website`)

---

## 🗂 Estrutura de Arquivos

| Arquivo | Descrição |
|---|---|
| [`Missionarios_Renovame.xlsx`](./Missionarios_Renovame.xlsx) | Arquivo XLSForm original em formato Excel (XLSX) para edição no Excel ou Kobo |
| [`Missionarios_Renovame.xls`](./Missionarios_Renovame.xls) | Cópia binária XLS compatível |
| [`Missionarios_Renovame.xml`](./Missionarios_Renovame.xml) | Definição compilada XForm XML (padrão OpenRosa/ODK) |
| [`Missionarios_Renovame_asset.json`](./Missionarios_Renovame_asset.json) | Metadados e schema JSON completo da API v2 do KoboToolbox |
| [`survey.csv`](./survey.csv) | Tabela CSV das perguntas e regras de validação |
| [`choices.csv`](./choices.csv) | Tabela CSV das opções de múltipla escolha (Gênero e Decisão) |
| [`settings.csv`](./settings.csv) | Configurações do formulário |
| [`media/Banner_renovam_vermelho.png`](./media/Banner_renovam_vermelho.png) | Banner de cabeçalho do formulário |
| [`media/Info_app_Kobotoolbox.jpg`](./media/Info_app_Kobotoolbox.jpg) | Imagem informativa/instruções |

---

## 📊 Campos do Formulário

| Campo (Nome) | Tipo | Rótulo (Label) | Dica (Hint) | Obrigatório | Regra / Opções |
|---|---|---|---|---|---|
| `deviceid` | `deviceid` | Metadado do Aparelho | - | Automático | Preenchimento automático pelo app |
| `Data` | `date` | Data | Data coletada automaticamente, por favor, clique em próximo. | Sim (`true`) | Padrão: `today()` |
| `Nome` | `text` | Nome | - | Sim (`true`) | Texto livre |
| `Idade` | `integer` | Idade | Insira apenas números | Sim (`true`) | Apenas números inteiros |
| `Telefone` | `text` | Telefone | - | Sim (`true`) | Regex: `^\d{11}$` (ex: `75988888888`) |
| `Genero` | `select_one dh9jq24` | Gênero | - | Sim (`true`) | Opções: `Masculino`, `Feminino` (layout horizontal) |
| `Recebeu_a_Jesus` | `select_one to0tn99` | Recebeu Jesus? | - | Sim (`true`) | Opções: `Sim`, `Não`, `É evangélico(a)`, `Ficou de decidir ainda` |
| `Endereco_ou_referencia` | `text` | Endereço ou referência | Opcional | Não (`false`) | Texto livre |
| `Geolocalizador` | `geopoint` | Geolocalizador | Clique em "obter ponto" para capturar a sua localização atual... | Sim (`true`) | Coordenadas GPS (latitude, longitude, altitude, precisão) |
| `Observacoes` | `text` | Observações | Opcional | Não (`false`) | Texto livre |
| `Nome_do_Mission_rio_a` | `text` | Nome do Missionário(a) | Por favor, informe seu nome que está preenchendo esta ficha | Sim (`true`) | Texto livre |

---

## 📱 Como Configurar o Aplicativo Móvel (KoBoCollect / ODK Collect)

No celular dos missionários, instale o **KoBoCollect** (disponível na Google Play Store) ou **ODK Collect**:

1. Abra o **KoBoCollect**.
2. Toque no ícone do perfil no canto superior direito e selecione **Configurações** (Settings) -> **Servidor** (Server).
3. Preencha os seguintes dados:
   - **URL:** `https://kobo.gabrielcjr.website` (ou `https://kobo.gabriel.website`)
   - **Nome de usuário:** `renovamechurch`
   - **Senha:** `Rvehonraegloria`
4. Volte para a tela inicial do aplicativo:
   - Toque em **Baixar formulário em branco** (Get Blank Form).
   - O aplicativo baixará automaticamente o formulário **Missionários Renova-me**.
5. Para coletar dados no campo:
   - Toque em **Preencher formulário em branco** (Fill Blank Form).
   - Responda as perguntas e toque em **Salvar formulário e sair**.
6. Para enviar os dados para o servidor:
   - Quando tiver conexão com a internet, toque em **Enviar formulário finalizado** (Send Finalized Form).
   - O formulário será sincronizado instantaneamente com o servidor Kubernetes.

---

## 🌐 Coleta Web (Sem Necessidade do Aplicativo)

O formulário também pode ser respondido diretamente pelo navegador em qualquer smartphone ou computador:
- **Link do Formulário Web:** `https://kobo.gabrielcjr.website/x/PY2hbkKi`

Recursos e Segurança da Informação:
- **Offline First & PWA:** Possui suporte a salvamento local no navegador se estiver sem conexão, enviando os dados automaticamente assim que a internet retornar.
- **Privacidade e Proteção de Dados:** Por segurança da informação, uma vez que o formulário é enviado ao servidor com sucesso, ele é imediatamente purgado do aparelho celular. Apenas rascunhos em andamento e envios pendentes de conexão permanecem no dispositivo.
- **Isolamento de Acesso:** O formulário não contém links nem acesso ao painel de controle administrativo, garantindo que o missionário em campo não acesse dados gerais ou coletas de outros membros.

---

## 💻 Painel Administrativo em Tempo Real e Exportação de Dados

Para visualizar todas as respostas coletadas e exportar para Excel/CSV:
- **Painel:** `https://kobo.gabrielcjr.website/dashboard`
- **Usuário:** `renovamechurch`
- **Senha:** `Rvehonraegloria`

Recursos do painel:
- **Atualização Automática ao Vivo:** Novos registros enviados pelos missionários aparecem instantaneamente na tabela e no mapa sem necessidade de recarregar a tela (Live Polling a cada 3 segundos).
- **Mapa Interativo (Leaflet):** Exibe a localização geográfica dos atendimentos realizados com coordenadas GPS.
- **Métricas e KPIs:** Indicadores consolidados de total de vidas cadastradas, decisões para Jesus, idade e ranking de missionários.
- **Exportação Multiformato:** Download direto em Excel (.xlsx), CSV e GeoJSON para sistemas GIS.


---

## 📈 Integração Direta com Google Planilhas (Google Sheets)

Para sincronizar automaticamente todas as fichas no Google Sheets em tempo real (exatamente como no serviço gratuito do KoBoToolbox):

1. Crie uma nova planilha no Google Sheets.
2. Na célula **A1**, cole a fórmula:
   ```excel
   =IMPORTDATA("https://kobo.gabrielcjr.website/api/v2/assets/a7FqboN3tiXKPo6hSc8MzJ/data.csv")
   ```

### 💡 Alternativa com Nomes Amigáveis em Português:
Se preferir os títulos das colunas e respostas em português:
```excel
=IMPORTDATA("https://kobo.gabrielcjr.website/api/v2/assets/a7FqboN3tiXKPo6hSc8MzJ/data.csv?labels=true")
```

*(URLs curtas equivalentes: `https://kobo.gabrielcjr.website/data.csv` ou `https://kobo.gabrielcjr.website/api/v1/data/a7FqboN3tiXKPo6hSc8MzJ.csv`)*

