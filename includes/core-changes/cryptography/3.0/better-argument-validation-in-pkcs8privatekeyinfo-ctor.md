---
ms.openlocfilehash: 32030698c12de87daef5e1d8851a0f55ec36d688
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721095"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a>Mejor validación de argumentos en el constructor de Pkcs8PrivateKeyInfo

A partir de la versión preliminar 9 de .NET Core 3.0, el constructor de `Pkcs8PrivateKeyInfo` valida el parámetro `algorithmParameters`como un único valor codificado en BER.

#### <a name="change-description"></a>Descripción del cambio

Antes de la versión preliminar 9 de .NET Core 3.0, el [constructor `Pkcs8PrivateKeyInfo`](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) no validó el argumento `algorithmParameters`.  Cuando este argumento represente un valor no válido, el constructor se realizará correctamente, pero una llamada a cualquiera de los métodos <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> o <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> produciría una <xref:System.ArgumentException>con un argumento que no aceptasen (`preEncodedValue`) o una <xref:System.Security.Cryptography.CryptographicException>.

Si se ejecuta con una versión preliminar de .NET Core 3.0 anterior a la 9, el código siguiente solo produce una excepción cuando se llama al método <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

A partir de la versión preliminar 9 de .NET Core 3.0, el argumento se valida en el constructor y un valor no válido se traduce en que el método produce una <xref:System.Security.Cryptography.CryptographicException>. Este cambio acerca la excepción al origen del error de datos. Por ejemplo:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 9)

#### <a name="recommended-action"></a>Acción recomendada

Asegúrese de que solo se especifiquen valores `algorithmParameters` válidos o, si se quiere un control de excepciones, de que se realicen llamadas a la prueba del constructor de `Pkcs8PrivateKeyInfo` tanto para <xref:System.ArgumentException> como para <xref:System.Security.Cryptography.CryptographicException>.

#### <a name="category"></a>Categoría

Criptografía

#### <a name="affected-apis"></a>API afectadas

- [Constructor de Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
