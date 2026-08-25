# Nexxus — Sistema de Emissão de NFS-e

> Plataforma de emissão, validação e gestão de notas fiscais de serviço eletrônica (NFS-e) no padrão nacional (Sistema Nacional NFS-e).

O **Nexxus** é um sistema web completo para a **FACC (Fundação de Apoio ao Desenvolvimento da Computação Científica)**, desenvolvido em ASP.NET Core, que unifica a emissão de DPS/NFS-e, o cadastro mestre de serviços, a validação com certificado digital e o controle financeiro.

---

## ✨ Funcionalidades

- **Emissão de DPS** no padrão nacional do Sistema NFS-e (SPED)
- **Cadastro mestre de serviços** com códigos de tributação (CTN, NBS, código municipal) preenchidos automaticamente
- **Validação contra o XSD oficial** da NFS-e (layout 1.01)
- **Assinatura digital** com certificado A1 (instalado no sistema) ou A3 (instalado no computador)
- **Envio ao ambiente de produção restrita** (homologação) do Sefin Nacional
- **Cancelamento de NFS-e** (evento e101101) com aba separada de notas canceladas
- **Gestão de tomadores** com busca automática por CPF/CNPJ
- **Relatórios financeiros** e exportação em Excel
- **Controle de projetos** vinculados às emissões
- **Gestão de usuários e equipes** por setor

---

## 🖥️ Telas do sistema

### Login

![Login](docs/login.png)

Tela de autenticação com visual moderno e acesso gerenciado pela equipe de TI.

### Formulário de emissão

![Formulário de emissão](docs/formulario.png)

Formulário de emissão da DPS com busca automática de tomador por CPF/CNPJ, cadastro mestre de serviços (dropdown com preenchimento automático de códigos), valor, vencimento e informações complementares.

### Lista de envios

![Lista de envios](docs/lista-envios.png)

Acompanhamento de todas as DPS geradas, com status de validação e envio.

### Validação

![Validação](docs/validacao.png)

Validação das DPS contra o XSD oficial, com assinatura digital e destaque dos erros de esquema.

### NFSe

![NFSe emitidas](docs/nfse.png)

Notas fiscais emitidas com chave de acesso, download do XML e opção de cancelamento.

### NFSe canceladas

![NFSe canceladas](docs/nfse-canceladas.png)

Notas canceladas separadas em aba própria, com motivo e data de cancelamento.

### Certificado digital

![Certificado digital](docs/certificado.png)

Instalação do certificado A1 no sistema para uso automático na validação, envio e cancelamento.

### Relatórios financeiros

![Relatórios financeiros](docs/relatorios.png)

Indicadores de receita, impostos e envios, com exportação em Excel.

### Projetos

![Projetos](docs/projetos.png)

Visão dos projetos vinculados às emissões de notas.

---

## 🚀 Tecnologias

- **Backend:** ASP.NET Core 8 (MVC)
- **Banco de dados:** SQLite (Entity Framework Core)
- **Frontend:** Bootstrap, JavaScript, Razor Pages
- **XML/Fiscal:** Geração e validação de DPS/eventos contra os XSD oficiais do Sistema Nacional NFS-e
- **Assinatura digital:** XMLDSig com certificados A1/A3 (ICP-Brasil)

---

## 🛠️ Configuração

### Pré-requisitos

- .NET 8 SDK
- Banco SQLite (criado automaticamente na primeira execução)

### Executar

```bash
cd nfse-web
dotnet run --urls http://0.0.0.0:5133
```

Acesse `http://localhost:5133`.

### Configuração (`appsettings.json`)

| Chave | Descrição |
|-------|-----------|
| `Nfse:TpAmb` | Ambiente (`1` produção, `2` homologação) |
| `Smtp` | Configuração de e-mail para envio das DPS |
| `Admin` | Credenciais iniciais do administrador |
| `PrestadorPadrao` | Dados do prestador (CNPJ, razão social, códigos de tributação) |

---

## 🔒 Segurança

- Senhas de usuário armazenadas com hash (BCrypt)
- Autenticação com cookies e controle de acesso por setor
- Certificado digital com senha persistida de forma controlada para uso automático
- Repositório privado no GitHub com `.gitignore` que exclui banco de dados, certificados e credenciais

---

## 📄 Licença

Uso interno da FACC — Fundação de Apoio ao Desenvolvimento da Computação Científica.
