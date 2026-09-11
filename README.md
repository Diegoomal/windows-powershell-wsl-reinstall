# Reinstalação limpa do WSL

## 1. Verificar distribuições instaladas

```powershell
wsl -l -v
```

## 2. Encerrar e desinstalar o runtime do WSL

```powershell
wsl --shutdown
wsl --uninstall
```

> Reinicie o Windows após esta etapa.

## 3. Reinstalar somente o WSL, sem distribuição Linux

```powershell
wsl --install --no-distribution --web-download
```

> Reinicie o Windows novamente após a instalação.

## 4. Validar o WSL e os arquivos do runtime

```powershell
wsl --version
wsl --status

Test-Path "C:\Program Files\WSL\system.vhd"
Test-Path "C:\Program Files\WSL\tools\modules.vhd"
```

Resultado esperado dos dois `Test-Path`:

```text
True
True
```

## 5. Instalar o Ubuntu

```powershell
wsl --install -d Ubuntu --web-download
```

## 6. Testar o Ubuntu

```powershell
wsl -d Ubuntu
```

## Ordem recomendada

WSL → validar WSL → Ubuntu → Docker
