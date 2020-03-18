---
ms.openlocfilehash: f9000b19997201c2d3de0643669f9029ff1ca31c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567953"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a>EnvelopedCms utiliza de forma predeterminada el cifrado AES-256

El algoritmo de cifrado simétrico predeterminado que usa `EnvelopedCms` ha cambiado de TripleDES a AES-256.

#### <a name="change-description"></a>Descripción del cambio

En la versión preliminar 7 de .NET Core y versiones anteriores, cuando se usa <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> para cifrar datos sin especificar un algoritmo de cifrado simétrico a través de una sobrecarga de constructor, los datos se cifran con el algoritmo TripleDES/3DES/3DEA/DES3-EDE.

A partir de la versión preliminar 8 de .NET Core 3.0 (a través de la versión 4.6.0 del paquete NuGet [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/)), el algoritmo predeterminado se ha cambiado a AES-256 para la modernización de algoritmos y para mejorar la seguridad de opciones predeterminadas. Si el certificado del destinatario de un mensaje tiene una clave pública Diffie-Hellman (no de cliente de empresa), es posible que se produzca un error <xref:System.Security.Cryptography.CryptographicException> en la operación de cifrado debido a limitaciones de la plataforma subyacente.

En el siguiente código de ejemplo, los datos se cifran con TripleDES si se ejecutan en la versión preliminar 7 de .NET Core 3.0 o en versiones anteriores. Si se ejecuta en la versión preliminar 8 de .NET Core 3.0 o versiones posteriores, se cifra con AES-256.

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

Si el cambio le afecta negativamente, puede restaurar el cifrado TripleDES especificando explícitamente el identificador del algoritmo de cifrado en un constructor de <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> que incluya un parámetro del tipo <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, por ejemplo:

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
