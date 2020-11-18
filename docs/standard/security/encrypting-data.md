---
title: Cifrar datos
description: Obtenga información sobre cómo cifrar datos en .NET mediante un algoritmo simétrico o asimétrico.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 574ef3f829406d661e19f004e9a7d150954fd9e5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830602"
---
# <a name="encrypting-data"></a>Cifrar datos

El cifrado simétrico y el cifrado asimétrico se efectúan mediante procesos distintos. El cifrado simétrico se realiza en secuencias y, por tanto, resulta útil para cifrar grandes cantidades de datos. El cifrado asimétrico se realiza en un pequeño número de bytes y, por tanto, solo resulta útil para pequeñas cantidades de datos.  
  
## <a name="symmetric-encryption"></a>Cifrado simétrico  

Las clases de criptografía simétrica administrada se usan con una clase de secuencia especial llamada <xref:System.Security.Cryptography.CryptoStream> que cifra los datos leídos en la secuencia. La clase **CryptoStream** se inicializa con una clase de secuencia administrada, una clase que implementa la <xref:System.Security.Cryptography.ICryptoTransform> interfaz (creada a partir de una clase que implementa un algoritmo criptográfico) y una <xref:System.Security.Cryptography.CryptoStreamMode> enumeración que describe el tipo de acceso permitido a **CryptoStream**. La clase **CryptoStream** puede inicializarse usando cualquier clase que derive de la <xref:System.IO.Stream> clase, incluidas <xref:System.IO.FileStream> , <xref:System.IO.MemoryStream> y <xref:System.Net.Sockets.NetworkStream> . Mediante estas clases, puede realizar el cifrado simétrico en diversos objetos de secuencia.  
  
En el ejemplo siguiente se muestra cómo crear una nueva instancia de la clase de implementación predeterminada para el <xref:System.Security.Cryptography.Aes> algoritmo. La instancia de se usa para realizar el cifrado en una clase **CryptoStream** . En este ejemplo, **CryptoStream** se inicializa con un objeto de secuencia llamado `myStream` que puede ser cualquier tipo de secuencia administrada. Al método **CreateEncryptor** de la clase **AES** se le pasa la clave y el IV que se usan para el cifrado. En este caso, se usan la clave predeterminada y el IV generados desde `aes` .
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
Después de ejecutar este código, los datos escritos en el objeto **CryptoStream** se cifran mediante el algoritmo AES.  
  
En el ejemplo siguiente se muestra todo el proceso de crear una secuencia, cifrarla, escribir en ella y cerrarla. En este ejemplo se crea una secuencia de archivos que se cifra mediante la clase **CryptoStream** y la clase **AES** . El IV generado se escribe en el principio de <xref:System.IO.FileStream> , por lo que se puede leer y usar para el descifrado. A continuación, se escribe un mensaje en la secuencia cifrada con la <xref:System.IO.StreamWriter> clase. Aunque se puede usar la misma clave varias veces para cifrar y descifrar los datos, se recomienda generar un nuevo IV aleatorio cada vez. De esta manera, los datos cifrados siempre son diferentes, incluso cuando el texto sin formato es el mismo.
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

El código cifra el flujo mediante el algoritmo simétrico de AES y escribe IV y después cifrado como "Hola mundo!" en la secuencia. Si el código es correcto, crea un archivo cifrado denominado *TestData.txt* y muestra el texto siguiente en la consola:
  
```console  
The text was encrypted.
```  

Puede descifrar el archivo mediante el ejemplo de descifrado simétrico en [descifrar datos](decrypting-data.md). Este ejemplo y este ejemplo especifican la misma clave.

Sin embargo, si se produce una excepción, el código muestra el texto siguiente en la consola:
  
```console  
The encryption failed.
```

## <a name="asymmetric-encryption"></a>Cifrado asimétrico

Los algoritmos asimétricos suelen usarse para cifrar pequeñas cantidades de datos, como el cifrado de una clave simétrica y un IV. Normalmente, cuando se realiza un cifrado asimétrico, se usa la clave pública generada por terceros. <xref:System.Security.Cryptography.RSA>.Net proporciona la clase para este propósito.  
  
En el ejemplo siguiente se usa la información de clave pública para cifrar una clave simétrica y un IV. Se inicializan dos matrices de bytes que representan la clave pública de un tercero. Se inicializa un objeto <xref:System.Security.Cryptography.RSAParameters> en estos valores. Después, el objeto **RSAParameters** (junto con la clave pública que representa) se importa en una instancia de **RSA** mediante el <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> método. Por último, se cifran la clave privada y el IV creados por una <xref:System.Security.Cryptography.Aes> clase. Este ejemplo requiere sistemas que tengan instalado el cifrado de 128 bits.  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
    End Sub

End Module
```  
  
```csharp  
using System;
using System.Security.Cryptography;

class Class1
{
    static void Main()
    {
        //Initialize the byte arrays to the public key information.  
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a>Vea también

- [Generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md)
- [Descifrar datos](decrypting-data.md)
- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [Vulnerabilidades de temporalización con descifrado simétrico en modo CBC al usar el relleno](vulnerabilities-cbc-mode.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
