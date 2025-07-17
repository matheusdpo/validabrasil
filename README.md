# 🇧🇷 ValidaBrasil

[![Go Version](https://img.shields.io/badge/Go-1.21+-blue.svg)](https://golang.org)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> 📋 Biblioteca em Go para validação de documentos brasileiros e formatos internacionais

Uma biblioteca completa e eficiente para validação de documentos brasileiros (CNPJ, CPF, CEP, RG, CNH), boletos, emails, URLs, endereços IP, cartões de crédito, números de celular e formatos monetários.

## 🚀 Características

- ✅ **Validação de CNPJ** - Com algoritmo de dígitos verificadores
- ✅ **Validação de CPF** - Com algoritmo de dígitos verificadores  
- ✅ **Validação de CEP** - Formato brasileiro (8 dígitos)
- ✅ **Validação de RG** - Múltiplos formatos estaduais
- ✅ **Validação de CNH** - Carteira Nacional de Habilitação
- ✅ **Validação de Data** - Múltiplos formatos (DD/MM/AAAA, AAAA-MM-DD, etc.)
- ✅ **Validação de Boleto** - Códigos de barras bancários
- ✅ **Validação de Email** - Formato RFC5322- ✅ **Validação de URL** - HTTP/HTTPS com regex robusto
- ✅ **Validação de IPv4/IPv6** - Endereços IP válidos
- ✅ **Validação de Cartão de Crédito** - Algoritmo de Luhn
- ✅ **Validação de Celular** - Nacional e internacional
- ✅ **Validação Monetária** - Formatos brasileiro e internacional

## 📦 Instalação

### Pré-requisitos

- Go 1.21 superior

### Via go get

```bash
go get github.com/matheusdpo/validabrasil
```

### Via go mod

```bash
go mod init meu-projeto
go get github.com/matheusdpo/validabrasil
```

## 🔧 Como Usar

### Importação

```go
import github.com/matheusdpo/validabrasil```

### Exemplo Básico

```go
package main

import (
   fmt"
    github.com/matheusdpo/validabrasil"
)

func main() [object Object]validator := validabrasil.NewValidator()
    
    // Validar CNPJ
    cnpjValido := validator.ValidarCNPJ("112220.333/0001-81)
    fmt.Printf(CNPJ válido: %t\n", cnpjValido)
    
    // Validar CPF
    cpfValido := validator.ValidarCPF(123.456.7899)
    fmt.Printf("CPF válido: %t\n", cpfValido)
    
    // Validar CEP
    cepValido := validator.ValidarCEP("123458)
    fmt.Printf("CEP válido: %t\n", cepValido)
    
    // Validar Email
    emailValido := validator.ValidarEmail("usuario@exemplo.com")
    fmt.Printf("Email válido: %t\n, emailValido)
}
```

### Exemplos Completos

#### Validação de Documentos Brasileiros

```go
validator := validabrasil.NewValidator()

// CNPJ
fmt.Println(validator.ValidarCNPJ("112220.33301-81/ true
fmt.Println(validator.ValidarCNPJ("111110.11111111)) // false

// CPF
fmt.Println(validator.ValidarCPF(123.456.789-9/ true
fmt.Println(validator.ValidarCPF(111.11111111)) // false

// CEP
fmt.Println(validator.ValidarCEP("12345678/ true
fmt.Println(validator.ValidarCEP(12345)) // false

// RG
fmt.Println(validator.ValidarRG("12.3450.678/ true
fmt.Println(validator.ValidarRG(123)) // false

// CNH
fmt.Println(validator.ValidarCNH(12345678901/ true
fmt.Println(validator.ValidarCNH("123))// false
```

#### Validação de Formatos Internacionais

```go
// Email
fmt.Println(validator.ValidarEmail("usuario@exemplo.com")) // true
fmt.Println(validator.ValidarEmail("usuario@")) // false

// URL
fmt.Println(validator.ValidarURL("https://www.exemplo.com")) // true
fmt.Println(validator.ValidarURL("exemplo")) // false

// IPv4
fmt.Println(validator.ValidarIPv4("192.1680.1")/ true
fmt.Println(validator.ValidarIPv4("2560.256560.56") // false

// IPv6
fmt.Println(validator.ValidarIPv6("2010db8:85a3:00000:8a270334")/ true
fmt.Println(validator.ValidarIPv6("10b8")) // false

// Cartão de Crédito
fmt.Println(validator.ValidarCartaoCredito("453215112830366"))/ true
fmt.Println(validator.ValidarCartaoCredito("1234567890123456"))// false
```

#### Validação de Telefones e Valores

```go
// Celular Nacional
fmt.Println(validator.ValidarCelularNacional((1199999/ true
fmt.Println(validator.ValidarCelularNacional(123) // false

// Celular Internacional
fmt.Println(validator.ValidarCelularInternacional("+15551234567/ true
fmt.Println(validator.ValidarCelularInternacional(123 // false

// Formato Monetário
fmt.Println(validator.ValidarFormatoMonetario(R$ 1.234,56")) // true
fmt.Println(validator.ValidarFormatoMonetario("$1,2340.56/ true
fmt.Println(validator.ValidarFormatoMonetario("1234)) // false
```

## 🧪 Testes

Para executar os testes:

```bash
go test ./...
```

Para executar com cobertura:

```bash
go test -cover ./...
```

## 📊 Benchmarks

```bash
go test -bench=. ./...
```

## 📁 Estrutura do Projeto

```
validabrasil/
├── README.md
├── validations.go
├── go.mod
├── go.sum
├── LICENSE
├── examples/
│   └── main.go
└── tests/
    └── validations_test.go
```

## 🤝 Contribuindo

Este é um projeto **open source** e todas as contribuições são bem-vindas! 

### Como Contribuir

1. **Fork** o projeto
2. Crie uma **branch** para sua feature (`git checkout -b feature/AmazingFeature`)
3*Commit** suas mudanças (`git commit -mAdd some AmazingFeature'`)
4sh** para a branch (`git push origin feature/AmazingFeature`)5 um **Pull Request**

### Diretrizes de Contribuição

- Mantenha o código limpo e bem documentado
- Adicione testes para novas funcionalidades
- Siga as convenções de nomenclatura do Go
- Atualize a documentação quando necessário

## 📄 Licença

Este projeto está licenciado sob a **MIT License** - veja o arquivo [LICENSE](LICENSE) para detalhes.

```
MIT License

Copyright (c)224Brasil

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 👨‍💻 Autor

**matheusdpo**


- 💼 **LinkedIn**: [matheus-de-paulo-oliveira](https://linkedin.com/in/matheus-de-paulo-oliveira)

- 📧 **Email**: matheusoliveira1991@hotmail.com

- 🐙 **GitHub**: [@matheusdpo](https://github.com/matheusdpo)

## 🌟 Agradecimentos

- Louvado seja Nosso Senhor Jesus Cristo e, para sempre seja louvado, com sua Mãe, Maria Santíssima!