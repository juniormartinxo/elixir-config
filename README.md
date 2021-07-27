#Instalando e configurando o Elixir no Windows

#h3 comando "iex" no PowerShell
Se você der o comando "Get-Alias -Name iex" no PowerShell irá verificar que este aliás é usado pelo Windows para invocar o Invoke-Expression e não o "iex.bat" do Elixir.
Então como eu devo fazer?
Simples, crie um aliás para o iex do Elixir!

Com o PowerShell aberto, digite 
...
Set-Alias -Name NOME_DO_ALIAS -Value CAMINHO_DO_ARQUIVO_IEX.BAT
...

Exemplo
...
Set-Alias -Name iexl -Value D:\DevTools\Elixir\bin\iex.bat
...
