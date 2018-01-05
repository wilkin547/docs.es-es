---
title: "Firmas criptográficas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 866d31662b8ae7d5c887af7d86007cb93a57d88f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="cryptographic-signatures"></a>Firmas criptográficas
<a name="top"></a> Las firmas digitales criptográficas usan algoritmos de clave pública para mantener la integridad de los datos. Si firma datos con una firma digital, otra persona puede comprobar la firma y confirmar que los datos provienen de usted y que no se han modificado después de ser firmados. Para más información sobre firmas digitales, vea [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).  
  
 En este tema se explica cómo generar y comprobar firmas digitales mediante clases en el espacio de nombres <xref:System.Security.Cryptography?displayProperty=nameWithType>.  
  
-   [Generación de firmas](#generate)  
  
-   [Comprobación de firmas](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a>Generación de firmas  
 Las firmas digitales suelen aplicarse a valores hash que representan datos de mayor volumen. En el siguiente ejemplo se aplica una firma digital a un valor hash. Primero se crea una instancia de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider> para generar un par de claves pública y privada. Después se pasa <xref:System.Security.Cryptography.RSACryptoServiceProvider> a una nueva instancia de la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> . Con esto se transfiere la clave privada a <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, que es el que realmente realiza la firma digital. Antes de poder firmar el código hash, hay que especificar el algoritmo hash que se usará. En este ejemplo se usa el algoritmo SHA1. Por último, se llama al método <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> para realizar el proceso de firma.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
    Sub Main()  
        'The hash value to sign.  
        Dim HashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}  
  
        'The value to hold the signed value.  
        Dim SignedHashValue() As Byte  
  
        'Generate a public/private key pair.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create an RSAPKCS1SignatureFormatter object and pass it   
        'the RSACryptoServiceProvider to transfer the private key.  
        Dim RSAFormatter As New RSAPKCS1SignatureFormatter(RSA)  
  
        'Set the hash algorithm to SHA1.  
        RSAFormatter.SetHashAlgorithm("SHA1")  
  
        'Create a signature for HashValue and assign it to   
        'SignedHashValue.  
        SignedHashValue = RSAFormatter.CreateSignature(HashValue)  
    End Sub  
End Module  
  
using System;  
using System.Security.Cryptography;  
```  
  
```csharp  
class Class1  
{  
   static void Main()  
   {  
      //The hash value to sign.  
      byte[] HashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};  
  
      //The value to hold the signed value.  
      byte[] SignedHashValue;  
  
      //Generate a public/private key pair.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create an RSAPKCS1SignatureFormatter object and pass it the   
      //RSACryptoServiceProvider to transfer the private key.  
      RSAPKCS1SignatureFormatter RSAFormatter = new RSAPKCS1SignatureFormatter(RSA);  
  
      //Set the hash algorithm to SHA1.  
      RSAFormatter.SetHashAlgorithm("SHA1");  
  
      //Create a signature for HashValue and assign it to   
      //SignedHashValue.  
      SignedHashValue = RSAFormatter.CreateSignature(HashValue);  
   }  
}  
```  
  
### <a name="signing-xml-files"></a>Firma de archivos XML  
 .NET Framework proporciona el espacio de nombres <xref:System.Security.Cryptography.Xml> , que permite firmar XML. Es importante firmar XML cuando se desea comprobar su procedencia. Por ejemplo, si usa un servicio de cotización de acciones que utiliza XML firmado, puede comprobar el origen del XML.  
  
 Las clases de este espacio de nombres siguen la [recomendación sobre procesamiento y sintaxis de firma de XML](http://go.microsoft.com/fwlink/?LinkId=136777) del World Wide Web Consortium.  
  
 [Volver al principio](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a>Comprobación de firmas  
 Para comprobar que alguien en concreto firmó los datos, es necesaria la información siguiente:  
  
-   La clave pública del firmante de los datos.  
  
-   La firma digital.  
  
-   Los datos que se firmaron.  
  
-   El algoritmo de hash usado por el firmante.  
  
 Para comprobar una firma realizada por la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , use la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> . A la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> debe proporcionársele la clave pública del firmante. Necesitará los valores del módulo y el exponente para especificar la clave pública. (Estos valores debe suministrarlos la parte que generó el par de claves pública y privada). Cree primero un <xref:System.Security.Cryptography.RSACryptoServiceProvider> objeto que contenga la clave pública que comprobará la firma y, a continuación, inicialice una <xref:System.Security.Cryptography.RSAParameters> estructura a los valores del módulo y del exponente que especifican la clave pública.  
  
 En el código siguiente se muestra la creación de una estructura <xref:System.Security.Cryptography.RSAParameters> . La propiedad `Modulus` se establece en el valor de una matriz de bytes denominada `ModulusData` y la propiedad `Exponent` se establece en el valor de una matriz de bytes denominada `ExponentData`.  
  
```vb  
Dim RSAKeyInfo As RSAParameters  
RSAKeyInfo.Modulus = ModulusData  
RSAKeyInfo.Exponent = ExponentData  
```  
  
```csharp  
RSAParameters RSAKeyInfo;  
RSAKeyInfo.Modulus = ModulusData;  
RSAKeyInfo.Exponent = ExponentData;  
```  
  
 Después de crear el objeto <xref:System.Security.Cryptography.RSAParameters> , puede inicializar una nueva instancia de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider> para los valores especificados en <xref:System.Security.Cryptography.RSAParameters>. <xref:System.Security.Cryptography.RSACryptoServiceProvider> a su vez, se pasa al constructor de un <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> para transferir la clave.  
  
 El ejemplo siguiente ilustra este proceso. En este ejemplo, `HashValue` y `SignedHashValue` son matrices de bytes que proporciona una parte remota. La parte remota firmó el `HashValue` mediante el algoritmo SHA1, produciendo así la firma digital `SignedHashValue`. A la clase  
  
 El método <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> comprueba que la firma digital es válida y que se usó para firmar el `HashValue`.  
  
```vb  
Dim RSA As New RSACryptoServiceProvider()  
RSA.ImportParameters(RSAKeyInfo)  
Dim RSADeformatter As New RSAPKCS1SignatureDeformatter(RSA)  
RSADeformatter.SetHashAlgorithm("SHA1")  
If RSADeformatter.VerifySignature(HashValue, SignedHashValue) Then  
   Console.WriteLine("The signature is valid.")  
Else  
   Console.WriteLine("The signture is not valid.")  
End If  
```  
  
```csharp  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
RSA.ImportParameters(RSAKeyInfo);  
RSAPKCS1SignatureDeformatter RSADeformatter = new RSAPKCS1SignatureDeformatter(RSA);  
RSADeformatter.SetHashAlgorithm("SHA1");  
if(RSADeformatter.VerifySignature(HashValue, SignedHashValue))  
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
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
