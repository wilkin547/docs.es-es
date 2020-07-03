---
title: Criptografía multiplataforma en .NET Core y .NET 5
description: Obtenga información sobre las capacidades criptográficas en las plataformas compatibles con .NET.
ms.date: 06/19/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- cryptography, cross-platform
- encryption, cross-platform
ms.openlocfilehash: 793a9bc55e5bd660374abd2ae81899e63ce3f36a
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85854030"
---
# <a name="cross-platform-cryptography-in-net-core-and-net-5"></a>Criptografía multiplataforma en .NET Core y .NET 5

Las operaciones criptográficas en .NET Core y .NET 5 las realizan las bibliotecas del sistema operativo (SO). Esta dependencia tiene ventajas:

* Las aplicaciones .NET se benefician de la confiabilidad del sistema operativo. Mantener la seguridad de las bibliotecas de criptografía de vulnerabilidades es una prioridad alta para los proveedores del sistema operativo. Para ello, proporcionan actualizaciones que los administradores del sistema deben aplicar.
* Las aplicaciones .NET tienen acceso a los algoritmos validados por FIPS si las bibliotecas del sistema operativo se validan por FIPS.

La dependencia de las bibliotecas del sistema operativo también significa que las aplicaciones .NET solo pueden usar las características criptográficas que admite el sistema operativo. Aunque todas las plataformas admiten determinadas características principales, algunas características que .NET admite no se pueden usar en algunas plataformas. En este artículo se identifican las características que se admiten en cada plataforma.

En este artículo se supone que está familiarizado con la criptografía en .NET. Para obtener más información, consulte [.net Cryptography Model](cryptography-model.md) y [.net Cryptographic Services](cryptographic-services.md).

## <a name="hash-algorithms"></a>Algoritmos hash

Todas las clases de algoritmo hash y de autenticación de mensajes basado en hash (HMAC), incluidas las `*Managed` clases, se aplazan a las bibliotecas del sistema operativo. Aunque las diversas bibliotecas de sistema operativo difieren en el rendimiento, deben ser compatibles.

## <a name="symmetric-encryption"></a>Cifrado simétrico

Las bibliotecas del sistema realizan los cifrados y el encadenamiento subyacentes, y todos son compatibles con todas las plataformas.

| Cifrado + modo | Windows | Linux | macOS |
|---------------|---------|-------|-------|
| AES-CBC       | ✔️     | ✔️    | ✔️   |
| NORMA AES       | ✔️     | ✔️    | ✔️   |
| 3DES-CBC      | ✔️     | ✔️    | ✔️   |
| 3DES-ECB      | ✔️     | ✔️    | ✔️   |
| DES-CBC       | ✔️     | ✔️    | ✔️   |
| DES-ECB       | ✔️     | ✔️    | ✔️   |

## <a name="authenticated-encryption"></a>Cifrado autenticado

Se proporciona compatibilidad con cifrado autenticado (AE) para AES-CCM y AES-GCM a través de las <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName> <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName> clases y.

En Windows y Linux, las implementaciones de AES-CCM y AES-GCM son proporcionadas por las bibliotecas del sistema operativo.

### <a name="aes-ccm-and-aes-gcm-on-macos"></a>AES-CCM y AES-GCM en macOS

En macOS, las bibliotecas del sistema no admiten AES-CCM o AES-GCM para código de terceros, por lo que las <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm> clases y usan OpenSSL para la compatibilidad. Los usuarios de macOS necesitan obtener una copia adecuada de OpenSSL (libcrypto) para que funcionen estos tipos, y deben estar en una ruta de acceso de la que el sistema cargue una biblioteca de forma predeterminada. Se recomienda instalar OpenSSL desde un administrador de paquetes como homebrew.

Las `libcrypto.0.9.7.dylib` `libcrypto.0.9.8.dylib` bibliotecas y incluidas en MacOS son de versiones anteriores de OpenSSL y no se usarán. Las `libcrypto.35.dylib` `libcrypto.41.dylib` bibliotecas, y `libcrypto.42.dylib` son de LibreSSL y no se usarán.

### <a name="aes-ccm-keys-nonces-and-tags"></a>Claves, nonces y etiquetas de AES-CCM

* Tamaños de clave

  AES-CCM funciona con claves 128, 192 y 256 bits.

* Tamaños de nonce

  La <xref:System.Security.Cryptography.AesCcm> clase admite 56, 64, 72, 80, 88, 96 y 104-bit (7, 8, 9, 10, 11, 12 y 13 bytes) nonces.

* Tamaños de etiqueta

  La <xref:System.Security.Cryptography.AesCcm> clase admite la creación o el procesamiento de las etiquetas 32, 48, 64, 80, 96, 112 y 128-bit (4, 8, 10, 12, 14 y 16 bytes).

### <a name="aes-gcm-keys-nonces-and-tags"></a>Claves de AES-GCM, nonces y etiquetas

* Tamaños de clave

  AES-GCM funciona con claves de 128, 192 y 256 bits.

* Tamaños de nonce

  La <xref:System.Security.Cryptography.AesGcm> clase solo admite nonces de 96 bits (12 bytes).

* Tamaños de etiqueta

  La <xref:System.Security.Cryptography.AesGcm> clase admite la creación o el procesamiento de las etiquetas 96, 104, 112, 120 y 128 bits (12, 13, 14, 15 y 16 bytes).

## <a name="asymmetric-cryptography"></a>Criptografía asimétrica

En esta sección se incluyen las siguientes subsecciones:

* [RSA](#rsa)
* [ECDSA](#ecdsa)
* [ECDH](#ecdh)
* [DSA](#dsa)

### <a name="rsa"></a>RSA

Las bibliotecas del sistema operativo realizan la generación de claves de RSA (Rivest – Shamir – Adleman) y está sujeta a sus limitaciones de tamaño y características de rendimiento.

Las operaciones de clave RSA las realizan las bibliotecas del sistema operativo y los tipos de clave que se pueden cargar están sujetos a los requisitos del sistema operativo.

.NET no expone operaciones RSA "sin procesar" (sin rellenar).

Las bibliotecas del sistema operativo se usan para el cifrado y el descifrado. No todas las plataformas admiten las mismas opciones de relleno:

| Modo de relleno                          | Windows (CNG) | Linux (OpenSSL) | macOS | Windows (CAPI) |
|---------------------------------------|---------------|-----------------|-------|----------------|
| Cifrado PKCS1                      | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP-SHA-1                          | ✔️           | ✔️              | ✔️   | ✔️             |
| OAEP-SHA-2 (SHA256, SHA384, SHA512) | ✔️           | ✔️              | ✔️   | ❌             |
| Firma PKCS1 (MD5, SHA-1)          | ✔️           | ✔️              | ✔️   | ✔️             |
| Firma PKCS1 (SHA-2)               | ✔️           | ✔️              | ✔️   | ⚠️\*           |
| PSS                                   | ✔️           | ✔️              | ✔️   | ❌             |

\*Windows CryptoAPI (CAPI) es capaz de la firma PKCS1 con un algoritmo SHA-2. Pero el objeto RSA individual se puede cargar en un proveedor de servicios criptográficos (CSP) que no lo admite.

#### <a name="rsa-on-windows"></a>RSA en Windows

* Se utiliza CryptoAPI de Windows (CAPI) siempre que [`new RSACryptoServiceProvider()`](xref:System.Security.Cryptography.RSACryptoServiceProvider) se use.
* Windows Cryptography API Next Generation (CNG) se usa siempre que [`new RSACng()`](xref:System.Security.Cryptography.RSACng) se usa.
* El objeto devuelto por <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> se basa internamente en CNG de Windows. Este uso de CNG de Windows es un detalle de implementación y está sujeto a cambios.
* El <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A> método de extensión de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> devuelve una <xref:System.Security.Cryptography.RSACng> instancia de. Este uso de <xref:System.Security.Cryptography.RSACng> es un detalle de implementación y está sujeto a cambios.
* El <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A> método de extensión para <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> prefiere una <xref:System.Security.Cryptography.RSACng> instancia, pero si <xref:System.Security.Cryptography.RSACng> no puede abrir la clave, se <xref:System.Security.Cryptography.RSACryptoServiceProvider> intentará. El proveedor preferido es un detalle de implementación y está sujeto a cambios.

#### <a name="rsa-native-interop"></a>Interoperabilidad nativa RSA

.NET expone tipos para permitir que los programas interoperen con las bibliotecas del sistema operativo que usa el código de criptografía de .NET. Los tipos implicados no se convierten entre plataformas y solo deben usarse directamente cuando sea necesario.

| Tipo                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.RSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup>| ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.RSACng>                   | ✔️     | ❌            | ❌            |
| <xref:System.Security.Cryptography.RSAOpenSsl>               | ❌     | ✔️            | ⚠️<sup>dos</sup> |

<sup>1</sup> en MacOS y Linux, <xref:System.Security.Cryptography.RSACryptoServiceProvider> se puede usar para la compatibilidad con programas existentes. En ese caso, cualquier método que requiera la interoperabilidad del sistema operativo, como abrir una clave con nombre, produce una excepción <xref:System.PlatformNotSupportedException> .

<sup>2</sup> en MacOS, <xref:System.Security.Cryptography.RSAOpenSsl> funciona si se instala OpenSSL y se puede encontrar un dylib de libcrypto adecuado a través de la carga de biblioteca dinámica. Si no se encuentra una biblioteca adecuada, se producirán excepciones.

### <a name="ecdsa"></a>ECDSA

Las bibliotecas del sistema operativo realizan la generación de claves ECDSA (algoritmo de firma digital de curva elíptica) y están sujetas a sus limitaciones de tamaño y características de rendimiento.

Las bibliotecas de sistema operativo definen las curvas de clave ECDSA y están sujetas a sus limitaciones.

| Curva elíptica                     | Windows 10    | Windows 7:8,1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| Curvas Brainpool (como curvas con nombre) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| Otras curvas con nombre                 | ⚠️<sup>dos</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| Curvas explícitas                    | ✔️           | ❌              | ✔️           | ❌            |
| Exportar o importar como explícito       | ✔️           | ❌<sup>3</sup>  | ✔️           | ❌<sup>3</sup>|

<sup>1</sup> las distribuciones de Linux no admiten todas las mismas curvas con nombre.

<sup>2</sup> se ha agregado compatibilidad con curvas con nombre a CNG de Windows en Windows 10. Para obtener más información, vea [CNG denominado curvas elípticas](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx). Las curvas con nombre no están disponibles en versiones anteriores de Windows, excepto para tres curvas en Windows 7.

<sup>3</sup> la exportación con parámetros de curva explícitos requiere compatibilidad con la biblioteca del sistema operativo, que no está disponible en MacOS o en versiones anteriores de Windows.

#### <a name="ecdsa-native-interop"></a>Interoperabilidad nativa ECDSA

.NET expone tipos para permitir que los programas interoperen con las bibliotecas del sistema operativo que usa el código de criptografía de .NET. Los tipos implicados no se convierten entre plataformas y solo deben usarse directamente cuando sea necesario.

| Tipo                                             | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDsaCng>     | ✔️     | ❌    | ❌    |
| <xref:System.Security.Cryptography.ECDsaOpenSsl> | ❌     | ✔️    | ⚠️\*  |

\*En macOS, <xref:System.Security.Cryptography.ECDsaOpenSsl> funciona si OpenSSL está instalado en el sistema y se puede encontrar un dylib libcrypto adecuado a través de la carga de biblioteca dinámica. Si no se encuentra una biblioteca adecuada, se producirán excepciones.

### <a name="ecdh"></a>ECDH

La generación de claves ECDH (Diffie-Hellman de curva elíptica) se realiza mediante las bibliotecas del sistema operativo y está sujeta a sus limitaciones de tamaño y características de rendimiento.

La <xref:System.Security.Cryptography.ECDiffieHellman> clase no devuelve el valor "RAW" del cálculo ECDH. Todos los datos devueltos están en términos de funciones de derivación de claves:

* HASH (Z)
* HASH (anteponer | | Z | | anexar
* HMAC (Key, Z)
* HMAC (clave, antepone | | Z | | anexar
* HMAC (Z, Z)
* HMAC (Z, antepone | | Z | | anexar
* Tls11Prf (etiqueta, SEED)

Las bibliotecas de sistema operativo definen las curvas de clave ECDH y están sujetas a sus limitaciones.

| Curva elíptica                     | Windows 10    | Windows 7:8,1 | Linux         | macOS         |
|------------------------------------|---------------|-----------------|---------------|---------------|
| NIST P-256 (secp256r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-384 (secp384r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| NIST P-521 (secp521r1)             | ✔️           | ✔️              | ✔️           | ✔️            |
| curvas Brainpool (como curvas con nombre) | ✔️           | ❌              | ⚠️<sup>1</sup>| ❌           |
| otras curvas con nombre                 | ⚠️<sup>dos</sup>| ❌             | ⚠️<sup>1</sup>| ❌           |
| curvas explícitas                    | ✔️           | ❌              | ✔️           | ❌            |
| Exportar o importar como explícito       | ✔️           | ❌<sup>3</sup>  | ✔️           | ❌<sup>3</sup>|

<sup>1</sup> las distribuciones de Linux no admiten todas las mismas curvas con nombre.

<sup>2</sup> se ha agregado compatibilidad con curvas con nombre a CNG de Windows en Windows 10. Para obtener más información, vea [CNG denominado curvas elípticas](https://msdn.microsoft.com/library/windows/desktop/mt632245(v=vs.85).aspx). Las curvas con nombre no están disponibles en versiones anteriores de Windows, excepto para tres curvas en Windows 7.

<sup>3</sup> la exportación con parámetros de curva explícitos requiere compatibilidad con la biblioteca del sistema operativo, que no está disponible en MacOS o en versiones anteriores de Windows.

#### <a name="ecdh-native-interop"></a>Interoperabilidad nativa ECDH

.NET expone tipos para permitir que los programas interoperen con las bibliotecas del sistema operativo que usa .NET. Los tipos implicados no se convierten entre plataformas y solo deben usarse directamente cuando sea necesario.

| Tipo                                                       | Windows | Linux | macOS |
|------------------------------------------------------------|---------|-------|-------|
| <xref:System.Security.Cryptography.ECDiffieHellmanCng>     | ✔️     | ❌    | ❌   |
| <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> | ❌     | ✔️    | ⚠️\* |

\*En macOS, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> funciona si se instala OpenSSL y se puede encontrar un dylib de libcrypto adecuado a través de la carga de biblioteca dinámica. Si no se encuentra una biblioteca adecuada, se producirán excepciones.

### <a name="dsa"></a>DSA

La generación de claves DSA (algoritmo de firma digital) se realiza mediante las bibliotecas del sistema y está sujeta a sus limitaciones de tamaño y características de rendimiento.

| Función                      | CNG de Windows | Linux | macOS         | CAPI de Windows |
|-------------------------------|-------------|-------|---------------|--------------|
| Creación de claves (<= 1024 bits)   | ✔️         | ✔️    | ❌            | ✔️           |
| Creación de claves (> bits 1024)    | ✔️         | ✔️    | ❌            | ❌            |
| Claves de carga (<= 1024 bits)   | ✔️         | ✔️    | ✔️            | ✔️           |
| Cargar claves (> bits 1024)    | ✔️         | ✔️    | ⚠️\*          | ❌            |
| FIPS 186-2                    | ✔️         | ✔️    | ✔️            | ✔️           |
| FIPS 186-3 (firmas SHA-2) | ✔️         | ✔️    | ❌            | ❌            |

\*macOS carga claves DSA mayores de 1024 bits, pero el comportamiento de esas claves es indefinido. No se comportan según FIPS 186-3.

#### <a name="dsa-on-windows"></a>DSA en Windows

* Se utiliza CryptoAPI de Windows (CAPI) siempre que [`new DSACryptoServiceProvider()`](xref:System.Security.Cryptography.DSACryptoServiceProvider) se use.
* Windows Cryptography API Next Generation (CNG) se usa siempre que [`new DSACng()`](xref:System.Security.Cryptography.DSACng) se usa.
* El objeto devuelto por <xref:System.Security.Cryptography.DSA.Create%2A?displayProperty=nameWithType> se basa internamente en CNG de Windows. Este uso de CNG de Windows es un detalle de implementación y está sujeto a cambios.
* El <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A> método de extensión de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> devuelve una <xref:System.Security.Cryptography.DSACng> instancia de. Este uso de <xref:System.Security.Cryptography.DSACng> es un detalle de implementación y está sujeto a cambios.
* El <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A> método de extensión para <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> prefiere una <xref:System.Security.Cryptography.DSACng> instancia, pero si <xref:System.Security.Cryptography.DSACng> no puede abrir la clave, se <xref:System.Security.Cryptography.DSACryptoServiceProvider> intentará.  El proveedor preferido es un detalle de implementación y está sujeto a cambios.

#### <a name="dsa-native-interop"></a>Interoperabilidad nativa DSA

.NET expone tipos para permitir que los programas interoperen con las bibliotecas del sistema operativo que usa el código de criptografía de .NET. Los tipos implicados no se convierten entre plataformas y solo deben usarse directamente cuando sea necesario.

| Tipo                                                         | Windows | Linux         | macOS         |
|--------------------------------------------------------------|---------|---------------|---------------|
| <xref:System.Security.Cryptography.DSACryptoServiceProvider> | ✔️     | ⚠️<sup>1</sup> | ⚠️<sup>1</sup> |
| <xref:System.Security.Cryptography.DSACng>                   | ✔️     | ❌             | ❌            |
| <xref:System.Security.Cryptography.DSAOpenSsl>               | ❌      | ✔️            | ⚠️<sup>dos</sup> |

<sup>1</sup> en MacOS y Linux, <xref:System.Security.Cryptography.DSACryptoServiceProvider> se puede usar para la compatibilidad con programas existentes. En ese caso, cualquier método que requiera la interoperabilidad del sistema, como abrir una clave con nombre, produce una excepción <xref:System.PlatformNotSupportedException> .

<sup>2</sup> en MacOS, <xref:System.Security.Cryptography.DSAOpenSsl> funciona si se instala OpenSSL y se puede encontrar un dylib de libcrypto adecuado a través de la carga de biblioteca dinámica. Si no se encuentra una biblioteca adecuada, se producirán excepciones.

## <a name="x509-certificates"></a>Certificados X.509

La mayoría de la compatibilidad con certificados X. 509 en .NET procede de las bibliotecas del sistema operativo. Para cargar un certificado en una <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> <xref:System.Security.Cryptography.X509Certificates.X509Certificate> instancia de o en .net, la biblioteca del sistema operativo subyacente debe cargar el certificado.

### <a name="read-a-pkcs12pfx"></a>Leer un archivo PKCS12/PFX

| Escenario                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Empty                                        | ✔️     | ✔️    | ✔️   |
| Un certificado, sin clave privada              | ✔️     | ✔️    | ✔️   |
| Un certificado, con clave privada            | ✔️     | ✔️    | ✔️   |
| Varios certificados, sin claves privadas       | ✔️     | ✔️    | ✔️   |
| Varios certificados, una clave privada       | ✔️     | ✔️    | ✔️   |
| Varios certificados, varias claves privadas | ✔️     | ⚠️\*  | ✔️   |

\*Disponible en las versiones de .NET 5 Preview.

### <a name="write-a-pkcs12pfx"></a>Escritura de PKCS12/PFX

| Escenario                                     | Windows | Linux | macOS |
|----------------------------------------------|---------|-------|-------|
| Empty                                        | ✔️     | ✔️    | ⚠️\* |
| Un certificado, sin clave privada              | ✔️     | ✔️    | ⚠️\* |
| Un certificado, con clave privada            | ✔️     | ✔️    | ✔️   |
| Varios certificados, sin claves privadas       | ✔️     | ✔️    | ⚠️\* |
| Varios certificados, una clave privada       | ✔️     | ✔️    | ✔️   |
| Varios certificados, varias claves privadas | ✔️     | ⚠️\*  | ✔️   |
| Carga efímera                            | ✔️     | ✔️    | ⚠️\* |

\*Disponible en las versiones de .NET 5 Preview.

macOS no puede cargar claves privadas de certificado sin un objeto de cadena de claves, lo que requiere escribir en el disco. Las llaves se crean automáticamente para la carga de PFX y se eliminan cuando ya no se usan. Dado que la <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> opción significa que la clave privada no debe escribirse en el disco, la aserción de la marca en MacOS da como resultado un <xref:System.PlatformNotSupportedException> .

### <a name="write-a-pkcs7-certificate-collection"></a>Escribir una colección de certificados PKCS7

Tanto Windows como Linux emiten blobs de PKCS7 codificados en DER. macOS emite blobs de PKCS7 con codificación de longitud ilimitada indefinida-CER.

### <a name="x509store"></a>X509Store

En Windows, la <xref:System.Security.Cryptography.X509Certificates.X509Store> clase es una representación de las API del almacén de certificados de Windows. Esas API funcionan igual en .NET Core y .NET 5 como en .NET Framework.

En Linux, la <xref:System.Security.Cryptography.X509Certificates.X509Store> clase es una proyección de las decisiones de confianza del sistema (solo lectura), las decisiones de confianza del usuario (lectura y escritura) y el almacenamiento de claves de usuario (lectura y escritura).

En macOS, la <xref:System.Security.Cryptography.X509Certificates.X509Store> clase es una proyección de las decisiones de confianza del sistema (solo lectura), las decisiones de confianza del usuario (solo lectura) y el almacenamiento de claves de usuario (lectura y escritura).

En las tablas siguientes se muestran los escenarios que se admiten en cada plataforma. En el caso de los escenarios no admitidos ( ❌ en las tablas), <xref:System.Security.Cryptography.CryptographicException> se produce una excepción.

#### <a name="the-my-store"></a>Mi tienda

| Escenario                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Abrir CurrentUser\My (ReadOnly)                   | ✔️     | ✔️    | ✔️   |
| Abrir CurrentUser\My (ReadWrite)                  | ✔️     | ✔️    | ✔️   |
| Abrir CurrentUser\My (ExistingOnly)               | ✔️     | ⚠️    | ✔️   |
| Abrir LocalMachine\My                             | ✔️     | ❌    | ✔️   |

En Linux, los almacenes se crean la primera vez que se escriben y no existen almacenes de usuarios de forma predeterminada, por lo `CurrentUser\My` `ExistingOnly` que es posible que se produzca un error al abrir con.

En macOS, el `CurrentUser\My` almacén es la cadena de claves predeterminada del usuario, que es de `login.keychain` forma predeterminada. El `LocalMachine\My` almacén es `System.keychain` .

#### <a name="the-root-store"></a>El almacén raíz

| Escenario                              | Windows | Linux | macOS           |
|---------------------------------------|---------|-------|-----------------|
| Abrir CurrentUser\Root (ReadOnly)      | ✔️     | ✔️    | ✔️             |
| Abrir CurrentUser\Root (ReadWrite)     | ✔️     | ✔️    | ❌              |
| Abrir CurrentUser\Root (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (si es de solo lectura) |
| Abrir LocalMachine\Root (ReadOnly)     | ✔️     | ✔️    | ✔️             |
| Abrir LocalMachine\Root (ReadWrite)    | ✔️     | ❌    | ❌              |
| Abrir LocalMachine\Root (ExistingOnly) | ✔️     | ⚠️    | ✔️ (si es de solo lectura) |

En Linux, el `LocalMachine\Root` almacén es una interpretación de la agrupación de entidades de certificación en la ruta de acceso predeterminada para OpenSSL.

En macOS, el `CurrentUser\Root` almacén es una interpretación de los `SecTrustSettings` resultados del dominio de confianza del usuario. El `LocalMachine\Root` almacén es una interpretación de los `SecTrustSettings` resultados de los dominios de administración y de confianza del sistema.

#### <a name="the-intermediate-store"></a>El almacén intermedio

| Escenario                                      | Windows | Linux | macOS           |
|-----------------------------------------------|---------|-------|-----------------|
| Abrir CurrentUser\Intermediate (ReadOnly)      | ✔️     | ✔️    | ✔️             |
| Abrir CurrentUser\Intermediate (ReadWrite)     | ✔️     | ✔️    | ❌              |
| Abrir CurrentUser\Intermediate (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (si es de solo lectura) |
| Abrir LocalMachine\Intermediate (ReadOnly)     | ✔️     | ✔️    | ✔️             |
| Abrir LocalMachine\Intermediate (ReadWrite)    | ✔️     | ❌    | ❌              |
| Abrir LocalMachine\Intermediate (ExistingOnly) | ✔️     | ⚠️    | ✔️ (si es de solo lectura) |

En Linux, el `CurrentUser\Intermediate` almacén se usa como una memoria caché cuando se descargan las CA intermedias mediante la información de autoridad acceso a los registros en compilaciones de X509Chain correctas. El `LocalMachine\Intermediate` almacén es una interpretación de la agrupación de entidades de certificación en la ruta de acceso predeterminada para OpenSSL.

#### <a name="the-disallowed-store"></a>Almacén no permitido

| Escenario                                    | Windows | Linux | macOS           |
|---------------------------------------------|---------|-------|-----------------|
| Abrir CurrentUser\Disallowed (ReadOnly)      | ✔️     | ⚠️    | ✔️             |
| Abrir CurrentUser\Disallowed (ReadWrite)     | ✔️     | ⚠️    | ❌              |
| Abrir CurrentUser\Disallowed (ExistingOnly)  | ✔️     | ⚠️    | ✔️ (si es de solo lectura) |
| Abrir LocalMachine\Disallowed (ReadOnly)     | ✔️     | ❌    | ✔️             |
| Abrir LocalMachine\Disallowed (ReadWrite)    | ✔️     | ❌    | ❌              |
| Abrir LocalMachine\Disallowed (ExistingOnly) | ✔️     | ❌    | ✔️ (si es de solo lectura) |

En Linux, el `Disallowed` almacén no se utiliza en la creación de cadenas y, al intentar agregar contenido a, se obtiene un <xref:System.Security.Cryptography.CryptographicException> . <xref:System.Security.Cryptography.CryptographicException>Se produce una excepción al abrir el `Disallowed` almacén si ya ha adquirido contenido.

En macOS, los almacenes CurrentUser\Disallowed y LocalMachine\Disallowed son interpretaciones de los resultados SecTrustSettings adecuados para los certificados cuya confianza está establecida en `Always Deny` .

#### <a name="nonexistent-store"></a>Almacén inexistente

| Escenario                                         | Windows | Linux | macOS |
|--------------------------------------------------|---------|-------|-------|
| Abrir el almacén no existente (ExistingOnly)           | ❌     | ❌     | ❌    |
| Abrir el almacén no existente de CurrentUser (ReadWrite)  | ✔️     | ✔️     | ⚠️   |
| Abrir almacén no existente LocalMachine (ReadWrite) | ✔️     | ❌     | ❌    |

En macOS, la creación de un almacén personalizado con la API X509Store solo se admite en la `CurrentUser` ubicación. Se creará una nueva cadena de claves sin contraseña en el directorio de cadena de claves del usuario (*~/Library/keychains*). Para crear una cadena de claves con la contraseña, `SecKeychainCreate` se podría usar P/Invoke. Del mismo modo, `SecKeychainOpen` se puede usar para abrir cadenas de claves en diferentes ubicaciones. El resultado `IntPtr` se puede pasar a [`new X509Store(IntPtr)`](xref:System.Security.Cryptography.X509Certificates.X509Store.%23ctor(System.IntPtr)) para obtener un almacén con capacidad de lectura/escritura, sujeto a los permisos del usuario actual.

### <a name="x509chain"></a>X509Chain

macOS no admite el uso de CRL sin conexión, por lo que `X509RevocationMode.Offline` se trata como `X509RevocationMode.Online` .

macOS no es compatible con un tiempo de espera Iniciado por el usuario en la descarga de CRL (lista de revocación de certificados)/OCSP (Protocolo de estado de certificados en línea)/AIA (acceso a la información de entidad), por lo que `X509ChainPolicy.UrlRetrievalTimeout` se omite.

## <a name="additional-resources"></a>Recursos adicionales

* [Modelo de criptografía de .NET](cryptography-model.md)
* [Servicios criptográficos .NET](cryptographic-services.md)
