# Criptografia
Anotações do estudo de Criptografia

# Assinatura de documento com iTextSharp
A White Paper by Bruno Lowagie (iText Software) [Veja aqui](https://sourceforge.net/p/itextsharp/code/HEAD/tree/tutorial/signatures/)  
Digital signature ebook [veja aqui](https://pages.itextpdf.com/ebook-digital-signatures-for-pdf.html)  
Digital signature ebook exemplos github [veja aqui](https://github.com/itext/i5ns-tutorial)
# Bibliotecas PKCS#11
Segue abaixo algumas biblioteca.  
* NCryptoki
  * [Cryptoki web site](www.ncryptoki.com)
* Projeto que implementa interoperabilidade com PKCS#11
  * [PKCS11 Interop](https://github.com/Pkcs11Interop)
* Projeto que implementa interoperabilidade com PKCS#11 PDF
  * [PKCS11 PDF](https://github.com/jariq/Pkcs11Interop.PDF)

# Manipulação de Chaves utilizando openssl
Segue exemplos de como manipular chaves utilizando openssl, converter chave para o formato p12.

## script criar chave, todas as etapas.

openssl genrsa -out server3.key 1024

#3 extrair a chave publica da chave privada
 
openssl rsa -in server3.key -pubout
 
## Generating a Certificate Signing Request
  
openssl req -new -key server3.key -out server3.csr 
 
## Signing Your Own Certificate 
openssl x509 -req -days 365 -in server3.csr -signkey server3.key -out server3.crt

## convert a certificate to pkcs#12 format
openssl pkcs12 -export -out certpcdf3.pfx -inkey server3.key -in server3.crt
