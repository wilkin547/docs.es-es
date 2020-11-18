---
title: Procedimiento para comprobar las firmas digitales de documentos XML
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSA class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
ms.openlocfilehash: 9cbebd34866b66c00bf4aca708d75e315b067b0d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820077"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="4c29d-102">Procedimiento para comprobar las firmas digitales de documentos XML</span><span class="sxs-lookup"><span data-stu-id="4c29d-102">How to: Verify the Digital Signatures of XML Documents</span></span>

<span data-ttu-id="4c29d-103">Puede usar las clases del espacio de nombres <xref:System.Security.Cryptography.Xml> para comprobar datos XML firmados con una firma digital.</span><span class="sxs-lookup"><span data-stu-id="4c29d-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="4c29d-104">Las firmas XML digitales (XMLDSIG) permiten comprobar que los datos no se modificaron después de firmarlos.</span><span class="sxs-lookup"><span data-stu-id="4c29d-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="4c29d-105">Para obtener más información sobre el estándar XMLDSIG, consulte la especificación de World Wide Web Consortium (W3C) en <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="4c29d-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c29d-106">El código de este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="4c29d-106">The code in this article applies to Windows.</span></span>

<span data-ttu-id="4c29d-107">En el ejemplo de código de este procedimiento se muestra cómo comprobar una firma digital XML incluida en un <`Signature` elemento>.</span><span class="sxs-lookup"><span data-stu-id="4c29d-107">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="4c29d-108">En el ejemplo se recupera una clave pública RSA de un contenedor de claves y se usa la clave para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="4c29d-108">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
<span data-ttu-id="4c29d-109">Para obtener información sobre cómo crear una firma digital que se pueda comprobar mediante esta técnica, consulte [Cómo: firmar documentos XML con firmas digitales](how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="4c29d-109">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="4c29d-110">Para comprobar la firma digital de un documento XML</span><span class="sxs-lookup"><span data-stu-id="4c29d-110">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="4c29d-111">Para comprobar el documento, debe usar la misma clave asimétrica que se empleó para la firma.</span><span class="sxs-lookup"><span data-stu-id="4c29d-111">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="4c29d-112">Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves usado para la firma.</span><span class="sxs-lookup"><span data-stu-id="4c29d-112">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="4c29d-113">Recupere la clave pública mediante la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="4c29d-113">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="4c29d-114">La clave se carga automáticamente desde el contenedor de claves por nombre al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="4c29d-114">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="4c29d-115">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="4c29d-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="4c29d-116">El objeto <xref:System.Xml.XmlDocument> contiene el documento XML firmado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="4c29d-116">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="4c29d-117">Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.SignedXml> y pásele el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="4c29d-117">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="4c29d-118">Busque el `signature` elemento <> y cree un nuevo <xref:System.Xml.XmlNodeList> objeto.</span><span class="sxs-lookup"><span data-stu-id="4c29d-118">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="4c29d-119">Cargue el XML del primer <`signature` elemento> en el <xref:System.Security.Cryptography.Xml.SignedXml> objeto.</span><span class="sxs-lookup"><span data-stu-id="4c29d-119">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="4c29d-120">Compruebe la firma con el método <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> y la clave pública RSA.</span><span class="sxs-lookup"><span data-stu-id="4c29d-120">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="4c29d-121">Este método devuelve un valor booleano que indica éxito o error.</span><span class="sxs-lookup"><span data-stu-id="4c29d-121">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="4c29d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c29d-122">Example</span></span>

<span data-ttu-id="4c29d-123">En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="4c29d-123">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="4c29d-124">El `"test.xml"` archivo se debe firmar mediante las técnicas descritas en [Cómo: firmar documentos XML con firmas digitales](how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="4c29d-124">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
[!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
[!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c29d-125">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4c29d-125">Compiling the Code</span></span>  
  
- <span data-ttu-id="4c29d-126">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="4c29d-126">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="4c29d-127">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="4c29d-127">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="4c29d-128">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="4c29d-128">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="4c29d-129">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="4c29d-129">.NET Security</span></span>

<span data-ttu-id="4c29d-130">Nunca almacene ni transfiera la clave privada de un par de claves asimétricas en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="4c29d-130">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="4c29d-131">Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="4c29d-131">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="4c29d-132">No inserte nunca una clave privada directamente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="4c29d-132">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="4c29d-133">Las claves incrustadas se pueden leer fácilmente desde un ensamblado mediante el [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="4c29d-133">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c29d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c29d-134">See also</span></span>

- [<span data-ttu-id="4c29d-135">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="4c29d-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="4c29d-136">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="4c29d-136">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="4c29d-137">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="4c29d-137">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="4c29d-138">Firmar documentos XML con firmas digitales</span><span class="sxs-lookup"><span data-stu-id="4c29d-138">How to: Sign XML Documents with Digital Signatures</span></span>](how-to-sign-xml-documents-with-digital-signatures.md)
- [<span data-ttu-id="4c29d-139">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="4c29d-139">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
