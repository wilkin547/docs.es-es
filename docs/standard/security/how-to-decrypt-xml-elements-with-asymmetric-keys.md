---
title: 'Cómo: Descifrar elementos XML con claves asimétricas'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
ms.openlocfilehash: 5ed1e2eb2518366da0a57655d7a8691e23f725d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706141"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="d44ed-102">Cómo: Descifrar elementos XML con claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="d44ed-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="d44ed-103">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar y descifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d44ed-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="d44ed-104">El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.</span><span class="sxs-lookup"><span data-stu-id="d44ed-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="d44ed-105">Para obtener más información sobre el estándar de cifrado XML, vea la recomendación del World Wide Web Consortium (W3C) [sintaxis y procesamiento de firmas XML](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="d44ed-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="d44ed-106">El ejemplo de este procedimiento descifra un elemento XML cifrado mediante los métodos descritos en [Cómo: cifrar elementos XML con claves asimétricas](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="d44ed-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="d44ed-107">Busca un <`EncryptedData`elemento >, descifra el elemento y, a continuación, reemplaza el elemento por el elemento XML de texto sin formato original.</span><span class="sxs-lookup"><span data-stu-id="d44ed-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="d44ed-108">En este ejemplo se descifra un elemento XML mediante dos claves.</span><span class="sxs-lookup"><span data-stu-id="d44ed-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="d44ed-109">Recupera una clave privada RSA generada previamente a partir de un contenedor de claves y, a continuación, usa la clave RSA para descifrar una clave de sesión almacenada en la <`EncryptedKey`elemento > del elemento <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="d44ed-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="d44ed-110">Luego, el ejemplo usa la clave de sesión para descifrar el elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d44ed-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="d44ed-111">Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="d44ed-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="d44ed-112">Para descifrar un elemento XML con una clave asimétrica</span><span class="sxs-lookup"><span data-stu-id="d44ed-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="d44ed-113">Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="d44ed-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="d44ed-114">Recupere una clave asimétrica previamente generada desde el contenedor mediante el objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="d44ed-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="d44ed-115">La clave se recupera automáticamente del contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="d44ed-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="d44ed-116">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> nuevo para descifrar el documento.</span><span class="sxs-lookup"><span data-stu-id="d44ed-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="d44ed-117">Agregue una asignación de clave/nombre para asociar la clave RSA al elemento del documento que se debe descifrar.</span><span class="sxs-lookup"><span data-stu-id="d44ed-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="d44ed-118">Debe usar el mismo nombre para la clave que usó al cifrar el documento.</span><span class="sxs-lookup"><span data-stu-id="d44ed-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="d44ed-119">Tenga en cuenta que este nombre es independiente del que haya usado para identificar la clave en el contenedor de claves especificado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="d44ed-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="d44ed-120">Llame al método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> para descifrar el elemento de >`EncryptedData`<.</span><span class="sxs-lookup"><span data-stu-id="d44ed-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="d44ed-121">Este método usa la clave RSA para descifrar la clave de sesión y la usa automáticamente para descifrar el elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d44ed-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="d44ed-122">También reemplaza automáticamente el <`EncryptedData`> elemento con el texto sin formato original.</span><span class="sxs-lookup"><span data-stu-id="d44ed-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="d44ed-123">Guarde el documento XML.</span><span class="sxs-lookup"><span data-stu-id="d44ed-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="d44ed-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d44ed-124">Example</span></span>  
 <span data-ttu-id="d44ed-125">En este ejemplo se supone que un archivo llamado `test.xml` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="d44ed-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="d44ed-126">También se supone que `test.xml` contiene un elemento XML que se cifró mediante las técnicas descritas en [Cómo: cifrar elementos XML con claves asimétricas](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="d44ed-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d44ed-127">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d44ed-127">Compiling the Code</span></span>  
  
- <span data-ttu-id="d44ed-128">Para compilar este ejemplo, debe incluir una referencia a `System.Security.dll`.</span><span class="sxs-lookup"><span data-stu-id="d44ed-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="d44ed-129">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="d44ed-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d44ed-130">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d44ed-130">.NET Framework Security</span></span>  
 <span data-ttu-id="d44ed-131">No almacene nunca una clave criptográfica simétrica en texto sin formato ni transfiera una clave simétrica entre equipos en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="d44ed-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="d44ed-132">Tampoco debe almacenar ni transferir nunca la clave privada de un par de claves asimétricas en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="d44ed-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="d44ed-133">Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="d44ed-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="d44ed-134">No inserte nunca una clave directamente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="d44ed-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="d44ed-135">Las claves incrustadas se pueden leer fácilmente desde un ensamblado mediante [Ildasm. exe (desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="d44ed-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="d44ed-136">Cuando termine de usar una clave criptográfica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.</span><span class="sxs-lookup"><span data-stu-id="d44ed-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="d44ed-137">A veces, las claves criptográficas se pueden leer desde la memoria con un depurador o desde un disco duro si la ubicación de memoria se pagina en el disco.</span><span class="sxs-lookup"><span data-stu-id="d44ed-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44ed-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d44ed-138">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="d44ed-139">Cifrar elementos XML con claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="d44ed-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
