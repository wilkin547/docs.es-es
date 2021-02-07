---
description: 'Más información acerca de cómo: descifrar elementos XML con claves asimétricas'
title: Procedimiento para descifrar elementos XML con claves asimétricas
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.RSA class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
ms.openlocfilehash: bd3bd142aa5800efa83bc20a4b1af6d5bc61eba2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675577"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="8dfea-103">Procedimiento para descifrar elementos XML con claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="8dfea-103">How to: Decrypt XML Elements with Asymmetric Keys</span></span>

<span data-ttu-id="8dfea-104">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar y descifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="8dfea-104">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="8dfea-105">El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.</span><span class="sxs-lookup"><span data-stu-id="8dfea-105">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="8dfea-106">Para obtener más información sobre el estándar de cifrado XML, vea la recomendación del World Wide Web Consortium (W3C) [sintaxis y procesamiento de firmas XML](https://www.w3.org/TR/xmldsig-core/).</span><span class="sxs-lookup"><span data-stu-id="8dfea-106">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  

> [!NOTE]
> <span data-ttu-id="8dfea-107">El código de este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="8dfea-107">The code in this article applies to Windows.</span></span>

<span data-ttu-id="8dfea-108">El ejemplo de este procedimiento descifra un elemento XML cifrado mediante los métodos descritos en [Cómo: cifrar elementos XML con claves asimétricas](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="8dfea-108">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="8dfea-109">Busca un elemento de `EncryptedData`> de <, descifra el elemento y, a continuación, reemplaza el elemento por el elemento XML de texto sin formato original.</span><span class="sxs-lookup"><span data-stu-id="8dfea-109">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="8dfea-110">En este ejemplo se descifra un elemento XML mediante dos claves.</span><span class="sxs-lookup"><span data-stu-id="8dfea-110">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="8dfea-111">Recupera una clave privada RSA generada previamente a partir de un contenedor de claves y, a continuación, usa la clave RSA para descifrar una clave de sesión almacenada en el `EncryptedKey` elemento <> del `EncryptedData` elemento> <.</span><span class="sxs-lookup"><span data-stu-id="8dfea-111">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="8dfea-112">Luego, el ejemplo usa la clave de sesión para descifrar el elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8dfea-112">The example then uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="8dfea-113">Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="8dfea-113">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="8dfea-114">Para descifrar un elemento XML con una clave asimétrica</span><span class="sxs-lookup"><span data-stu-id="8dfea-114">To decrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="8dfea-115">Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="8dfea-115">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="8dfea-116">Recupere una clave asimétrica previamente generada desde el contenedor mediante el objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="8dfea-116">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="8dfea-117">La clave se recupera automáticamente del contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="8dfea-117">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="8dfea-118">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> nuevo para descifrar el documento.</span><span class="sxs-lookup"><span data-stu-id="8dfea-118">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. <span data-ttu-id="8dfea-119">Agregue una asignación de clave/nombre para asociar la clave RSA al elemento del documento que se debe descifrar.</span><span class="sxs-lookup"><span data-stu-id="8dfea-119">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="8dfea-120">Debe usar el mismo nombre para la clave que usó al cifrar el documento.</span><span class="sxs-lookup"><span data-stu-id="8dfea-120">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="8dfea-121">Tenga en cuenta que este nombre es independiente del que haya usado para identificar la clave en el contenedor de claves especificado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="8dfea-121">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. <span data-ttu-id="8dfea-122">Llame al <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> método para descifrar el elemento de> de <`EncryptedData` .</span><span class="sxs-lookup"><span data-stu-id="8dfea-122">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="8dfea-123">Este método usa la clave RSA para descifrar la clave de sesión y la usa automáticamente para descifrar el elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8dfea-123">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="8dfea-124">También reemplaza automáticamente el elemento <`EncryptedData`> por el texto sin formato original.</span><span class="sxs-lookup"><span data-stu-id="8dfea-124">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. <span data-ttu-id="8dfea-125">Guarde el documento XML.</span><span class="sxs-lookup"><span data-stu-id="8dfea-125">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="8dfea-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dfea-126">Example</span></span>

<span data-ttu-id="8dfea-127">En este ejemplo se supone que un archivo llamado `test.xml` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="8dfea-127">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="8dfea-128">También se supone que `test.xml` contiene un elemento XML cifrado mediante las técnicas descritas en [Cómo: cifrar elementos XML con claves asimétricas](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="8dfea-128">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
[!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8dfea-129">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8dfea-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="8dfea-130">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="8dfea-130">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="8dfea-131">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="8dfea-131">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="8dfea-132">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="8dfea-132">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="8dfea-133">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="8dfea-133">.NET Security</span></span>  

<span data-ttu-id="8dfea-134">No almacene nunca una clave criptográfica simétrica en texto sin formato ni transfiera una clave simétrica entre equipos en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="8dfea-134">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="8dfea-135">Tampoco debe almacenar ni transferir nunca la clave privada de un par de claves asimétricas en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="8dfea-135">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="8dfea-136">Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="8dfea-136">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="8dfea-137">No inserte nunca una clave directamente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="8dfea-137">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="8dfea-138">Las claves incrustadas se pueden leer fácilmente desde un ensamblado mediante [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="8dfea-138">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="8dfea-139">Cuando termine de usar una clave criptográfica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.</span><span class="sxs-lookup"><span data-stu-id="8dfea-139">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="8dfea-140">A veces, las claves criptográficas se pueden leer desde la memoria con un depurador o desde un disco duro si la ubicación de memoria se pagina en el disco.</span><span class="sxs-lookup"><span data-stu-id="8dfea-140">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfea-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dfea-141">See also</span></span>

- [<span data-ttu-id="8dfea-142">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="8dfea-142">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="8dfea-143">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="8dfea-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="8dfea-144">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="8dfea-144">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="8dfea-145">Cifrar elementos XML con claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="8dfea-145">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
- [<span data-ttu-id="8dfea-146">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="8dfea-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
