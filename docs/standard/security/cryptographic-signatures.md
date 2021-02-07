---
description: 'Más información acerca de: firmas criptográficas'
title: Firmas criptográficas
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET], signatures
- security [.NET], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
ms.openlocfilehash: 082f55af648b73b6447d69edd5912804e9332d03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685301"
---
# <a name="cryptographic-signatures"></a>Firmas criptográficas

Las firmas digitales criptográficas usan algoritmos de clave pública para mantener la integridad de los datos. Si firma datos con una firma digital, otra persona puede comprobar la firma y confirmar que los datos provienen de usted y que no se han modificado después de ser firmados. Para más información sobre firmas digitales, vea [Cryptographic Services](cryptographic-services.md).

En este tema se explica cómo generar y comprobar firmas digitales mediante clases en el espacio de nombres <xref:System.Security.Cryptography> .

## <a name="generating-signatures"></a>Generación de firmas

Las firmas digitales suelen aplicarse a valores hash que representan datos de mayor volumen. En el siguiente ejemplo se aplica una firma digital a un valor hash. Primero se crea una instancia de la clase <xref:System.Security.Cryptography.RSA> para generar un par de claves pública y privada. Después se pasa <xref:System.Security.Cryptography.RSA> a una nueva instancia de la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> . Con esto se transfiere la clave privada a <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, que es el que realmente realiza la firma digital. Antes de poder firmar el código hash, hay que especificar el algoritmo hash que se usará. En este ejemplo se usa el algoritmo SHA1. Por último, se llama al método <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> para realizar el proceso de firma.

Debido a problemas de colisión con SHA1, se recomienda SHA256 o superior.

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As RSA = RSA.Create()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSA instance to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
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
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSA rsa = RSA.Create();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSA instance to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

## <a name="verifying-signatures"></a>Comprobación de firmas

Para comprobar que alguien en concreto firmó los datos, es necesaria la información siguiente:

- La clave pública del firmante de los datos.

- La firma digital.

- Los datos que se firmaron.

- El algoritmo de hash usado por el firmante.

Para comprobar una firma realizada por la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , use la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> . A la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> debe proporcionársele la clave pública del firmante. Para RSA, necesitará los valores del módulo y el exponente para especificar la clave pública. (La entidad que generó el par de claves pública y privada debe proporcionar estos valores). En primer lugar <xref:System.Security.Cryptography.RSA> , cree un objeto que contenga la clave pública que comprobará la firma y, a continuación, inicialice una <xref:System.Security.Cryptography.RSAParameters> estructura a los valores de módulo y exponente que especifican la clave pública.

En el código siguiente se muestra la creación de una estructura <xref:System.Security.Cryptography.RSAParameters> . La propiedad `Modulus` se establece en el valor de una matriz de bytes denominada `modulusData` y la propiedad `Exponent` se establece en el valor de una matriz de bytes denominada `exponentData`.

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

Una vez creado el <xref:System.Security.Cryptography.RSAParameters> objeto, puede inicializar una nueva instancia de la <xref:System.Security.Cryptography.RSA> clase de implementación con los valores especificados en <xref:System.Security.Cryptography.RSAParameters> . <xref:System.Security.Cryptography.RSA>A su vez, la instancia se pasa al constructor de un <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> para transferir la clave.

El ejemplo siguiente ilustra este proceso. En este ejemplo, `hashValue` y `signedHashValue` son matrices de bytes que proporciona una parte remota. La parte remota firmó el `hashValue` mediante el algoritmo SHA1, produciendo así la firma digital `signedHashValue`. El <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> método comprueba que la firma digital es válida y que se usó para firmar el `hashValue` .

Debido a problemas de colisión con SHA1, se recomienda SHA256 o superior.  Sin embargo, si se utilizó SHA1 para crear la firma, debe utilizar SHA1 para comprobar la firma.

```vb
Dim rsa As RSA = RSA.Create()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSA rsa = RSA.Create();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

Este fragmento de código mostrará "`The signature is valid`" si la firma es válida y "`The signature is not valid`" si no lo es.

## <a name="see-also"></a>Vea también

- [servicios criptográficos](cryptographic-services.md)
- [Modelo de criptografía](cryptography-model.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
