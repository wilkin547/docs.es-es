---
title: Firmas criptográficas
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f9d83a0edb6dc2261931e422b0ae4c735d2e0d1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086101"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="fdad8-102">Firmas criptográficas</span><span class="sxs-lookup"><span data-stu-id="fdad8-102">Cryptographic Signatures</span></span>
<a name="top"></a> <span data-ttu-id="fdad8-103">Las firmas digitales criptográficas usan algoritmos de clave pública para mantener la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="fdad8-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="fdad8-104">Si firma datos con una firma digital, otra persona puede comprobar la firma y confirmar que los datos provienen de usted y que no se han modificado después de ser firmados.</span><span class="sxs-lookup"><span data-stu-id="fdad8-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="fdad8-105">Para más información sobre firmas digitales, vea [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="fdad8-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>  
  
 <span data-ttu-id="fdad8-106">En este tema se explica cómo generar y comprobar firmas digitales mediante clases en el espacio de nombres <xref:System.Security.Cryptography?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fdad8-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
-   [<span data-ttu-id="fdad8-107">Generación de firmas</span><span class="sxs-lookup"><span data-stu-id="fdad8-107">Generating Signatures</span></span>](#generate)  
  
-   [<span data-ttu-id="fdad8-108">Comprobación de firmas</span><span class="sxs-lookup"><span data-stu-id="fdad8-108">Verifying Signatures</span></span>](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a><span data-ttu-id="fdad8-109">Generación de firmas</span><span class="sxs-lookup"><span data-stu-id="fdad8-109">Generating Signatures</span></span>  
 <span data-ttu-id="fdad8-110">Las firmas digitales suelen aplicarse a valores hash que representan datos de mayor volumen.</span><span class="sxs-lookup"><span data-stu-id="fdad8-110">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="fdad8-111">En el siguiente ejemplo se aplica una firma digital a un valor hash.</span><span class="sxs-lookup"><span data-stu-id="fdad8-111">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="fdad8-112">Primero se crea una instancia de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider> para generar un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="fdad8-112">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="fdad8-113">Después se pasa <xref:System.Security.Cryptography.RSACryptoServiceProvider> a una nueva instancia de la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> .</span><span class="sxs-lookup"><span data-stu-id="fdad8-113">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="fdad8-114">Con esto se transfiere la clave privada a <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, que es el que realmente realiza la firma digital.</span><span class="sxs-lookup"><span data-stu-id="fdad8-114">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="fdad8-115">Antes de poder firmar el código hash, hay que especificar el algoritmo hash que se usará.</span><span class="sxs-lookup"><span data-stu-id="fdad8-115">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="fdad8-116">En este ejemplo se usa el algoritmo SHA1.</span><span class="sxs-lookup"><span data-stu-id="fdad8-116">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="fdad8-117">Por último, se llama al método <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> para realizar el proceso de firma.</span><span class="sxs-lookup"><span data-stu-id="fdad8-117">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>  
  
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
  
### <a name="signing-xml-files"></a><span data-ttu-id="fdad8-118">Firma de archivos XML</span><span class="sxs-lookup"><span data-stu-id="fdad8-118">Signing XML Files</span></span>  
 <span data-ttu-id="fdad8-119">.NET Framework proporciona el espacio de nombres <xref:System.Security.Cryptography.Xml> , que permite firmar XML.</span><span class="sxs-lookup"><span data-stu-id="fdad8-119">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="fdad8-120">Es importante firmar XML cuando se desea comprobar su procedencia.</span><span class="sxs-lookup"><span data-stu-id="fdad8-120">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="fdad8-121">Por ejemplo, si usa un servicio de cotización de acciones que utiliza XML firmado, puede comprobar el origen del XML.</span><span class="sxs-lookup"><span data-stu-id="fdad8-121">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>  
  
 <span data-ttu-id="fdad8-122">Las clases de este espacio de nombres siguen la [recomendación de XML-Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/) del World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="fdad8-122">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>  
  
 [<span data-ttu-id="fdad8-123">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="fdad8-123">Back to top</span></span>](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a><span data-ttu-id="fdad8-124">Comprobación de firmas</span><span class="sxs-lookup"><span data-stu-id="fdad8-124">Verifying Signatures</span></span>  
 <span data-ttu-id="fdad8-125">Para comprobar que alguien en concreto firmó los datos, es necesaria la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdad8-125">To verify that data was signed by a particular party, you must have the following information:</span></span>  
  
-   <span data-ttu-id="fdad8-126">La clave pública del firmante de los datos.</span><span class="sxs-lookup"><span data-stu-id="fdad8-126">The public key of the party that signed the data.</span></span>  
  
-   <span data-ttu-id="fdad8-127">La firma digital.</span><span class="sxs-lookup"><span data-stu-id="fdad8-127">The digital signature.</span></span>  
  
-   <span data-ttu-id="fdad8-128">Los datos que se firmaron.</span><span class="sxs-lookup"><span data-stu-id="fdad8-128">The data that was signed.</span></span>  
  
-   <span data-ttu-id="fdad8-129">El algoritmo de hash usado por el firmante.</span><span class="sxs-lookup"><span data-stu-id="fdad8-129">The hash algorithm used by the signer.</span></span>  
  
 <span data-ttu-id="fdad8-130">Para comprobar una firma realizada por la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , use la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> .</span><span class="sxs-lookup"><span data-stu-id="fdad8-130">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="fdad8-131">A la clase <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> debe proporcionársele la clave pública del firmante.</span><span class="sxs-lookup"><span data-stu-id="fdad8-131">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="fdad8-132">Necesitará los valores del módulo y el exponente para especificar la clave pública.</span><span class="sxs-lookup"><span data-stu-id="fdad8-132">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="fdad8-133">(Estos valores debe suministrarlos la parte que generó el par de claves pública y privada). En primer lugar cree un <xref:System.Security.Cryptography.RSACryptoServiceProvider> objeto para contener la clave pública que comprobará la firma y, a continuación, inicialice una <xref:System.Security.Cryptography.RSAParameters> a los valores de módulo y del exponente que especifican la clave pública.</span><span class="sxs-lookup"><span data-stu-id="fdad8-133">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>  
  
 <span data-ttu-id="fdad8-134">En el código siguiente se muestra la creación de una estructura <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="fdad8-134">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="fdad8-135">La propiedad `Modulus` se establece en el valor de una matriz de bytes denominada `ModulusData` y la propiedad `Exponent` se establece en el valor de una matriz de bytes denominada `ExponentData`.</span><span class="sxs-lookup"><span data-stu-id="fdad8-135">The `Modulus` property is set to the value of a byte array called `ModulusData` and the `Exponent` property is set to the value of a byte array called `ExponentData`.</span></span>  
  
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
  
 <span data-ttu-id="fdad8-136">Después de crear el objeto <xref:System.Security.Cryptography.RSAParameters> , puede inicializar una nueva instancia de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider> para los valores especificados en <xref:System.Security.Cryptography.RSAParameters>.</span><span class="sxs-lookup"><span data-stu-id="fdad8-136">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="fdad8-137"><xref:System.Security.Cryptography.RSACryptoServiceProvider> a su vez, se pasa al constructor de un <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> para transferir la clave.</span><span class="sxs-lookup"><span data-stu-id="fdad8-137">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>  
  
 <span data-ttu-id="fdad8-138">El ejemplo siguiente ilustra este proceso.</span><span class="sxs-lookup"><span data-stu-id="fdad8-138">The following example illustrates this process.</span></span> <span data-ttu-id="fdad8-139">En este ejemplo, `HashValue` y `SignedHashValue` son matrices de bytes que proporciona una parte remota.</span><span class="sxs-lookup"><span data-stu-id="fdad8-139">In this example, `HashValue` and `SignedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="fdad8-140">La parte remota firmó el `HashValue` mediante el algoritmo SHA1, produciendo así la firma digital `SignedHashValue`.</span><span class="sxs-lookup"><span data-stu-id="fdad8-140">The remote party has signed the `HashValue` using the SHA1 algorithm, producing the digital signature `SignedHashValue`.</span></span> <span data-ttu-id="fdad8-141">A la clase</span><span class="sxs-lookup"><span data-stu-id="fdad8-141">The</span></span>  
  
 <span data-ttu-id="fdad8-142">El método <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> comprueba que la firma digital es válida y que se usó para firmar el `HashValue`.</span><span class="sxs-lookup"><span data-stu-id="fdad8-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `HashValue`.</span></span>  
  
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
  
 <span data-ttu-id="fdad8-143">Este fragmento de código mostrará "`The signature is valid`" si la firma es válida y "`The signature is not valid`" si no lo es.</span><span class="sxs-lookup"><span data-stu-id="fdad8-143">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdad8-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdad8-144">See also</span></span>

- [<span data-ttu-id="fdad8-145">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="fdad8-145">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
