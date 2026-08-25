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

<img width="1400" height="761" alt="image" src="https://github.com/user-attachments/assets/5007eb48-0963-4420-9958-10da4cfe7135" />


Tela de autenticação com visual moderno e acesso gerenciado pela equipe de TI.

### Formulário de emissão

<img width="1400" height="761" alt="image" src="https://github.com/user-attachments/assets/4e58b6b8-b49e-4dde-9e23-e7b08947606f" />


Formulário de emissão da DPS com busca automática de tomador por CPF/CNPJ, cadastro mestre de serviços (dropdown com preenchimento automático de códigos), valor, vencimento e informações complementares.

### Lista de envios

<img width="1892" height="830" alt="image" src="https://github.com/user-attachments/assets/33842906-5349-4e00-a0c3-a5c6c70b33d1" />


Acompanhamento de todas as DPS geradas, com status de validação e envio.

### Validação


<img width="1892" height="903" alt="image" src="https://github.com/user-attachments/assets/0843d422-4f77-42fd-95e4-b052a0659903" />



Validação das DPS contra o XSD oficial, com assinatura digital e destaque dos erros de esquema.

### NFSe

<img width="1895" height="891" alt="image" src="https://github.com/user-attachments/assets/e91024c3-f8b8-491f-98a7-75b52c994689" />


Notas fiscais emitidas com chave de acesso, download do XML e opção de cancelamento.

### NFSe canceladas

<img width="1899" height="890" alt="image" src="https://github.com/user-attachments/assets/29f72463-8dda-4647-9895-47aecdeab4d4" />


Notas canceladas separadas em aba própria, com motivo e data de cancelamento.

### Certificado digital

<img width="1894" height="892" alt="image" src="https://github.com/user-attachments/assets/11f9d3c5-6ecf-4fac-ac3e-777f958a1128" />



Instalação do certificado A1 no sistema para uso automático na validação, envio e cancelamento.

### Relatórios financeiros

<img width="1898" height="888" alt="image" src="https://github.com/user-attachments/assets/03cddf98-003a-4be6-8494-d03fa0746450" />


Indicadores de receita, impostos e envios, com exportação em Excel.

### Projetos

<img width="1894" height="889" alt="image" src="https://github.com/user-attachments/assets/f653aa13-fe79-4746-b60c-30380eb2934f" />


Visão dos projetos vinculados às emissões de notas.

---

## 🚀 Tecnologias

- **Backend:** ASP.NET Core 8 (MVC)
- **Banco de dados:** SQLite (Entity Framework Core)
- **Frontend:** Bootstrap, JavaScript, Razor Pages
- **XML/Fiscal:** Geração e validação de DPS/eventos contra os XSD oficiais do Sistema Nacional NFS-e
- **Assinatura digital:** XMLDSig com certificados A1/A3 (ICP-Brasil)

---


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


## Desenvolvido por

| | |
|---|---|
| **Julia Santos** | [@ttpmorp](https://github.com/ttpmorp) · [ttpmorp@proton.me](mailto:ttpmorp@proton.me) |
