# Instalando e configurando o Elixir no Windows

## O Comando "iex" do PowerShell
Se você der o comando *__"Get-Alias -Name iex"__* no PowerShell, provavelmente receberá a seguinte saída no terminal:
```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           iex -> Invoke-Expression
```

Ou seja, o comando __*"iex nativo"*__ é um aliás utilizado pelo Windows para invocar o cmdlet __*Invoke-Expression*__ e não o *__"iex.bat"__* do Elixir.

#### Então, como eu devo fazer?
Simples, crie um aliás para o __*"iex"*__ do Elixir:

**1)** Com o PowerShell aberto, digite:
```
Set-Alias -Name NOME_DO_ALIAS -Value CAMINHO_DO_ARQUIVO_IEX.BAT
```

>*__Exemplo:__*
```
Set-Alias -Name iexl -Value D:\DevTools\Elixir\bin\iex.bat
```
>**Atenção:** O problema ainda não está resolvido, pois se você fechar e abrir o PowerShell novamente o aliás que você criou vai parar de funcionar. Para resolver faça o seguinte:

**2)** Crie o ou edite o seu arquivo PROFILE do PowerShell, e para isso, com o PowerShell aberto digite:
```
if (!(Test-Path -Path $PROFILE)) {
   New-Item -ItemType File -Path $PROFILE -Force
}
```
O comando acima irá cria um arquivo PROFILE caso ele não exista.

**3)** Criado o arquivo do PROFILE você deverá editar o seu conteúdo, para isso, digite no terminal o seguinte comando:
```
notepad $PROFILE
```
**4)** O comando acima irá abrir o arquivo PROFILE criado, agora basta inserir o comando do **passo 1**, que de acordo com o exemplo dado fica:
```
Set-Alias -Name iexl -Value D:\DevTools\Elixir\bin\iex.bat
```
**5)** Feche e salve o arquivo PROFILE e pronto, seu novo aliás estará salvo.

#### Referências
- [Microsoft - Set-Alias](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.1&viewFallbackFrom=powershell-6)
- [Microsoft - About_profiles](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-7.1)
