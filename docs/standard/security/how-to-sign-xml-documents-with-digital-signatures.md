---
title: Procedimiento para firmar documentos XML con firmas digitales
description: Obtenga información sobre cómo firmar documentos XML con firmas digitales. Use las clases en el espacio de nombres System.Security.Cryptography.Xml en .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSA class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
ms.openlocfilehash: e1457fd659ab63489bd4cfafd7731a4b098a2791
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557078"
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a><span data-ttu-id="12a4d-104">Procedimiento para firmar documentos XML con firmas digitales</span><span class="sxs-lookup"><span data-stu-id="12a4d-104">How to: Sign XML Documents with Digital Signatures</span></span>

<span data-ttu-id="12a4d-105">Puede usar las clases del espacio de nombres <xref:System.Security.Cryptography.Xml> para firmar un documento XML o parte de un documento XML con una firma digital.</span><span class="sxs-lookup"><span data-stu-id="12a4d-105">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to sign an XML document or part of an XML document with a digital signature.</span></span>  <span data-ttu-id="12a4d-106">Las firmas XML digitales (XMLDSIG) permiten comprobar que los datos no se modificaron después de firmarlos.</span><span class="sxs-lookup"><span data-stu-id="12a4d-106">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span>  <span data-ttu-id="12a4d-107">Para obtener más información sobre el estándar XMLDSIG, consulte la recomendación de la [firma XML](https://www.w3.org/TR/xmldsig-core/)del World Wide Web Consortium (W3C) y el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="12a4d-107">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12a4d-108">El código de este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="12a4d-108">The code in this article applies to Windows.</span></span>

<span data-ttu-id="12a4d-109">En el ejemplo de código de este procedimiento se muestra cómo firmar digitalmente un documento XML completo y adjuntar la firma al documento en un <`Signature` elemento>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-109">The code example in this procedure demonstrates how to digitally sign an entire XML document and attach the signature to the document in a <`Signature`> element.</span></span>  <span data-ttu-id="12a4d-110">En el ejemplo se crea una clave de firma RSA, se agrega la clave a un contenedor de claves seguro y, a continuación, se usa la clave para firmar digitalmente un documento XML.</span><span class="sxs-lookup"><span data-stu-id="12a4d-110">The example creates an RSA signing key, adds the key to a secure key container, and then uses the key to digitally sign an XML document.</span></span>  <span data-ttu-id="12a4d-111">La clave se puede recuperar para comprobar la firma digital XML, o bien se puede usar para firmar otro documento XML.</span><span class="sxs-lookup"><span data-stu-id="12a4d-111">The key can then be retrieved to verify the XML digital signature, or can be used to sign another XML document.</span></span>  
  
<span data-ttu-id="12a4d-112">Para obtener información sobre cómo comprobar una firma digital XML creada con este procedimiento, consulte [Cómo: comprobar las firmas digitales de documentos XML](how-to-verify-the-digital-signatures-of-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="12a4d-112">For information about how to verify an XML digital signature that was created using this procedure, see [How to: Verify the Digital Signatures of XML Documents](how-to-verify-the-digital-signatures-of-xml-documents.md).</span></span>  
  
### <a name="to-digitally-sign-an-xml-document"></a><span data-ttu-id="12a4d-113">Para firmar digitalmente un documento XML</span><span class="sxs-lookup"><span data-stu-id="12a4d-113">To digitally sign an XML document</span></span>  
  
1. <span data-ttu-id="12a4d-114">Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="12a4d-114">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="12a4d-115">Genere una clave asimétrica mediante la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-115">Generate an asymmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="12a4d-116">La clave se guarda automáticamente en el contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-116">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="12a4d-117">Esta clave se usará para firmar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="12a4d-117">This key will be used to sign the XML document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="12a4d-118">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="12a4d-118">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="12a4d-119">El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a cifrar.</span><span class="sxs-lookup"><span data-stu-id="12a4d-119">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="12a4d-120">Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.SignedXml> y pásele el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-120">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="12a4d-121">Agregue la clave RSA de firma al objeto <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-121">Add the signing RSA key to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="12a4d-122">Cree un objeto <xref:System.Security.Cryptography.Xml.Reference> que describa qué se va a firmar.</span><span class="sxs-lookup"><span data-stu-id="12a4d-122">Create a <xref:System.Security.Cryptography.Xml.Reference> object that describes what to sign.</span></span>  <span data-ttu-id="12a4d-123">Para firmar el documento completo, establezca la propiedad <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> en `""`.</span><span class="sxs-lookup"><span data-stu-id="12a4d-123">To sign the entire document, set the <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> property to `""`.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="12a4d-124">Agregue un objeto <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> al objeto <xref:System.Security.Cryptography.Xml.Reference>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-124">Add an <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> object to the <xref:System.Security.Cryptography.Xml.Reference> object.</span></span>  <span data-ttu-id="12a4d-125">Una transformación permite al comprobador representar los datos XML de un modo idéntico al que usó el firmante.</span><span class="sxs-lookup"><span data-stu-id="12a4d-125">A transformation allows the verifier to represent the XML data in the identical manner that the signer used.</span></span>  <span data-ttu-id="12a4d-126">Los datos XML se pueden representar de maneras diferentes, por lo que este paso es vital para la comprobación.</span><span class="sxs-lookup"><span data-stu-id="12a4d-126">XML data can be represented in different ways, so this step is vital to verification.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8. <span data-ttu-id="12a4d-127">Agregue el objeto <xref:System.Security.Cryptography.Xml.Reference> al objeto <xref:System.Security.Cryptography.Xml.SignedXml>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-127">Add the <xref:System.Security.Cryptography.Xml.Reference> object to the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. <span data-ttu-id="12a4d-128">Calcule la firma llamando al método <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-128">Compute the signature by calling the <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A> method.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. <span data-ttu-id="12a4d-129">Recuperar la representación XML de la firma (un `Signature` elemento <>) y guardarla en un nuevo <xref:System.Xml.XmlElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="12a4d-129">Retrieve the XML representation of the signature (a <`Signature`> element) and save it to a new <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. <span data-ttu-id="12a4d-130">Anexe el elemento al objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-130">Append the element to the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. <span data-ttu-id="12a4d-131">Guarde el documento.</span><span class="sxs-lookup"><span data-stu-id="12a4d-131">Save the document.</span></span>  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="12a4d-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12a4d-132">Example</span></span>  
 <span data-ttu-id="12a4d-133">En este ejemplo se supone que un archivo llamado `test.xml` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="12a4d-133">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="12a4d-134">Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="12a4d-134">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12a4d-135">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="12a4d-135">Compiling the Code</span></span>  
  
- <span data-ttu-id="12a4d-136">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="12a4d-136">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="12a4d-137">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="12a4d-137">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="12a4d-138">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="12a4d-138">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="12a4d-139">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="12a4d-139">.NET Security</span></span>

<span data-ttu-id="12a4d-140">Nunca almacene ni transfiera la clave privada de un par de claves asimétricas en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="12a4d-140">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="12a4d-141">Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="12a4d-141">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="12a4d-142">No inserte nunca una clave privada directamente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="12a4d-142">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="12a4d-143">Las claves incrustadas se pueden leer fácilmente desde un ensamblado mediante el [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="12a4d-143">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a4d-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12a4d-144">See also</span></span>

- [<span data-ttu-id="12a4d-145">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="12a4d-145">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="12a4d-146">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="12a4d-146">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="12a4d-147">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="12a4d-147">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="12a4d-148">Procedimiento para comprobar las firmas digitales de documentos XML</span><span class="sxs-lookup"><span data-stu-id="12a4d-148">How to: Verify the Digital Signatures of XML Documents</span></span>](how-to-verify-the-digital-signatures-of-xml-documents.md)
- [<span data-ttu-id="12a4d-149">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="12a4d-149">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
