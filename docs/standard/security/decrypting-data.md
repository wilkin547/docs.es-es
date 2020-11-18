---
title: Descifrar datos
description: Obtenga información acerca de cómo descifrar datos en .NET mediante un algoritmo simétrico o asimétrico.
ms.date: 07/16/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: cf286eeca8a9372c6532c56701e4775d5e09d786
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831109"
---
# <a name="decrypting-data"></a>Descifrar datos

El descifrado es la operación inversa del cifrado. Para el cifrado de clave secreta, debe conocer la clave y el IV que se usaron para cifrar los datos. Para el cifrado de clave pública, debe conocer la clave pública (si los datos se cifraron mediante la clave privada) o la clave privada (si los datos se cifran mediante la clave pública).

## <a name="symmetric-decryption"></a>Descifrado simétrico

El descifrado de los datos cifrados con algoritmos simétricos es similar al proceso usado para cifrar datos con algoritmos simétricos. La <xref:System.Security.Cryptography.CryptoStream> clase se usa con las clases de criptografía simétricas proporcionadas por .net para descifrar los datos leídos de cualquier objeto de secuencia administrado.

En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo. La instancia se utiliza para realizar el descifrado en un <xref:System.Security.Cryptography.CryptoStream> objeto. En primer lugar, en este ejemplo se crea una nueva instancia de la <xref:System.Security.Cryptography.Aes> clase de implementación. Lee el valor del vector de inicialización (IV) de una variable de secuencia administrada, `myStream` . A continuación, se crea una instancia <xref:System.Security.Cryptography.CryptoStream> de un objeto y se inicializa en el valor de la `myStream` instancia. Al <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> método de la <xref:System.Security.Cryptography.Aes> instancia se le pasa el valor de IV y la misma clave que se usó para el cifrado.

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, descifrarla, leer en ella y cerrarla. Se crea un objeto de secuencia de archivos que lee un archivo denominado *TestData.txt*. A continuación, el flujo de archivo se descifra con la clase **CryptoStream** y la clase **AES** . En este ejemplo se especifica el valor de clave que se usa en el ejemplo de cifrado simétrico para [cifrar datos](encrypting-data.md). No se muestra el código necesario para cifrar y transferir estos valores.

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

En el ejemplo anterior se utiliza la misma clave y el algoritmo utilizado en el ejemplo de cifrado simétrico para [cifrar datos](encrypting-data.md). Descifra el archivo de *TestData.txt* que se crea en ese ejemplo y muestra el texto original en la consola.

## <a name="asymmetric-decryption"></a>Descifrado asimétrico

Normalmente, una parte (parte A) genera tanto una clave pública como privada y la almacena en memoria o en un contenedor de claves criptográficas. A continuación, la parte A envía la clave pública a otra parte (parte B). Mediante el uso de la clave pública, la parte B cifra los datos y envía los datos de vuelta a la entidad A. Después de recibir los datos, la parte A los descifra mediante la clave privada correspondiente. El descifrado será correcto solo si la parte A usa la clave privada que corresponde a la clave pública que la parte B usó para cifrar los datos.

Para obtener información sobre cómo almacenar una clave asimétrica en un contenedor de claves criptográficas seguro y cómo recuperar posteriormente la clave asimétrica, consulte [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).

En el ejemplo siguiente se muestra el descifrado de dos matrices de bytes que representan una clave simétrica y un IV. Para obtener información sobre cómo extraer la clave pública asimétrica del objeto <xref:System.Security.Cryptography.RSA> en un formato que se pueda enviar fácilmente a un tercero, consulte [Encrypting Data](encrypting-data.md).

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a>Vea también

- [Generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md)
- [Cifrar datos](encrypting-data.md)
- [servicios criptográficos](cryptographic-services.md)
- [Modelo de criptografía](cryptography-model.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno](vulnerabilities-cbc-mode.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
