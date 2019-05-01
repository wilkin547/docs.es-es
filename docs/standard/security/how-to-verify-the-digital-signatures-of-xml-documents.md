---
title: Procedimiento para comprobar las firmas digitales de documentos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSACryptoServiceProvider class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19537fa3e3e27c3446d22f1f1a8cf2faf472158e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018572"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="09f25-102">Procedimiento para comprobar las firmas digitales de documentos XML</span><span class="sxs-lookup"><span data-stu-id="09f25-102">How to: Verify the Digital Signatures of XML Documents</span></span>
<span data-ttu-id="09f25-103">Puede usar las clases del espacio de nombres <xref:System.Security.Cryptography.Xml> para comprobar datos XML firmados con una firma digital.</span><span class="sxs-lookup"><span data-stu-id="09f25-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="09f25-104">Las firmas XML digitales (XMLDSIG) permiten comprobar que los datos no se modificaron después de firmarlos.</span><span class="sxs-lookup"><span data-stu-id="09f25-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="09f25-105">Para obtener más información sobre el estándar XMLDSIG, consulte la especificación de World Wide Web Consortium (W3C) en <https://www.w3.org/TR/xmldsig-core/>.</span><span class="sxs-lookup"><span data-stu-id="09f25-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
 <span data-ttu-id="09f25-106">El ejemplo de código en este procedimiento muestra cómo comprobar una firma digital XML contenida en un <`Signature`> elemento.</span><span class="sxs-lookup"><span data-stu-id="09f25-106">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="09f25-107">En el ejemplo se recupera una clave pública RSA de un contenedor de claves y se usa la clave para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="09f25-107">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
 <span data-ttu-id="09f25-108">Para obtener información acerca de cómo crear una firma digital que se pueda comprobar mediante esta técnica, consulte [Cómo: Firmar documentos XML con firmas digitales](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="09f25-108">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="09f25-109">Para comprobar la firma digital de un documento XML</span><span class="sxs-lookup"><span data-stu-id="09f25-109">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="09f25-110">Para comprobar el documento, debe usar la misma clave asimétrica que se empleó para la firma.</span><span class="sxs-lookup"><span data-stu-id="09f25-110">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="09f25-111">Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves usado para la firma.</span><span class="sxs-lookup"><span data-stu-id="09f25-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="09f25-112">Recupere la clave pública mediante la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="09f25-112">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="09f25-113">La clave se carga automáticamente desde el contenedor de claves por nombre al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="09f25-113">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="09f25-114">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="09f25-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="09f25-115">El objeto <xref:System.Xml.XmlDocument> contiene el documento XML firmado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="09f25-115">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="09f25-116">Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.SignedXml> y pásele el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="09f25-116">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="09f25-117">Buscar el <`signature`> elemento y crear un nuevo <xref:System.Xml.XmlNodeList> objeto.</span><span class="sxs-lookup"><span data-stu-id="09f25-117">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="09f25-118">Cargar el XML del primer <`signature`> elemento en el <xref:System.Security.Cryptography.Xml.SignedXml> objeto.</span><span class="sxs-lookup"><span data-stu-id="09f25-118">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="09f25-119">Compruebe la firma con el método <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> y la clave pública RSA.</span><span class="sxs-lookup"><span data-stu-id="09f25-119">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="09f25-120">Este método devuelve un valor booleano que indica éxito o error.</span><span class="sxs-lookup"><span data-stu-id="09f25-120">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="09f25-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09f25-121">Example</span></span>  
 <span data-ttu-id="09f25-122">En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="09f25-122">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="09f25-123">El `"test.xml"` debe firmarse mediante las técnicas descritas en el archivo [Cómo: Firmar documentos XML con firmas digitales](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="09f25-123">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="09f25-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="09f25-124">Compiling the Code</span></span>  
  
- <span data-ttu-id="09f25-125">Para compilar este ejemplo, debe incluir una referencia a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="09f25-125">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="09f25-126">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="09f25-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="09f25-127">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09f25-127">.NET Framework Security</span></span>  
 <span data-ttu-id="09f25-128">Nunca almacene ni transfiera la clave privada de un par de claves asimétricas en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="09f25-128">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="09f25-129">Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="09f25-129">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="09f25-130">No inserte nunca una clave privada directamente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="09f25-130">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="09f25-131">Las claves insertadas se pueden leer fácilmente desde un ensamblado mediante la [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="09f25-131">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f25-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="09f25-132">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="09f25-133">Cómo: Firmar documentos XML con firmas digitales</span><span class="sxs-lookup"><span data-stu-id="09f25-133">How to: Sign XML Documents with Digital Signatures</span></span>](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)
