---
description: 'Más información acerca de cómo: cifrar elementos XML con claves asimétricas'
title: Procedimiento para cifrar elementos XML con claves asimétricas
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- AES algorithm
- System.Security.Cryptography.RSA class
- asymmetric keys [.NET]
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- key containers
- Advanced Encryption Standard algorithm
- encryption [.NET], asymmetric keys
ms.assetid: a164ba4f-e596-4bbe-a9ca-f214fe89ed48
ms.openlocfilehash: fff8ec57da0318e48f2a230f01dba26497837028
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685158"
---
# <a name="how-to-encrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="f2964-103">Procedimiento para cifrar elementos XML con claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="f2964-103">How to: Encrypt XML Elements with Asymmetric Keys</span></span>

<span data-ttu-id="f2964-104">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2964-104">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="f2964-105">El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.</span><span class="sxs-lookup"><span data-stu-id="f2964-105">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="f2964-106">Para obtener más información sobre el estándar de cifrado XML, consulte la especificación de World Wide Web Consortium (W3C) para el cifrado XML ubicado en <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="f2964-106">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="f2964-107">Puede usar el cifrado de XML para reemplazar cualquier elemento o documento XML con un elemento <`EncryptedData`> que contenga los datos XML cifrados.</span><span class="sxs-lookup"><span data-stu-id="f2964-107">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span>  <span data-ttu-id="f2964-108">El `EncryptedData` elemento <> también puede contener subelementos que incluyan información sobre las claves y los procesos usados durante el cifrado.</span><span class="sxs-lookup"><span data-stu-id="f2964-108">The <`EncryptedData`> element can also contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="f2964-109">El cifrado XML permite que un documento contenga varios elementos cifrados y permite cifrar varias veces un elemento.</span><span class="sxs-lookup"><span data-stu-id="f2964-109">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="f2964-110">En el ejemplo de código de este procedimiento se muestra cómo crear un `EncryptedData` elemento <> junto con otros subelementos que se pueden usar posteriormente durante el descifrado.</span><span class="sxs-lookup"><span data-stu-id="f2964-110">The code example in this procedure shows how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
 <span data-ttu-id="f2964-111">En este ejemplo se cifra un elemento XML mediante dos claves.</span><span class="sxs-lookup"><span data-stu-id="f2964-111">This example encrypts an XML element using two keys.</span></span>  <span data-ttu-id="f2964-112">Genera un par de claves públicas/privadas RSA y lo guarda en un contenedor de claves seguras.</span><span class="sxs-lookup"><span data-stu-id="f2964-112">It generates an RSA public/private key pair and saves the key pair to a secure key container.</span></span>  <span data-ttu-id="f2964-113">A continuación, en el ejemplo se crea una clave de sesión independiente mediante el algoritmo Estándar de cifrado avanzado (AES).</span><span class="sxs-lookup"><span data-stu-id="f2964-113">The example then creates a separate session key using the Advanced Encryption Standard (AES) algorithm.</span></span>  <span data-ttu-id="f2964-114">El ejemplo usa la clave de sesión AES para cifrar el documento XML y usa la clave pública RSA para cifrar la clave de sesión AES.</span><span class="sxs-lookup"><span data-stu-id="f2964-114">The example uses the AES session key to encrypt the XML document and then uses the RSA public key to encrypt the AES session key.</span></span>  <span data-ttu-id="f2964-115">Por último, en el ejemplo se guarda la clave de sesión AES cifrada y los datos XML cifrados en el documento XML dentro de un nuevo <`EncryptedData`> elemento.</span><span class="sxs-lookup"><span data-stu-id="f2964-115">Finally, the example saves the encrypted AES session key and the encrypted XML data to the XML document within a new <`EncryptedData`> element.</span></span>  
  
 <span data-ttu-id="f2964-116">Para descifrar el elemento XML, recupere la clave privada RSA del contenedor de claves, úsela para descifrar la clave de sesión y, posteriormente, descifrar el documento.</span><span class="sxs-lookup"><span data-stu-id="f2964-116">To decrypt the XML element, you retrieve the RSA private key from the key container, use it to decrypt the session key, and then use the session key to decrypt the document.</span></span>  <span data-ttu-id="f2964-117">Para obtener más información sobre cómo descifrar un elemento XML cifrado mediante este procedimiento, vea [Cómo: descifrar elementos XML con claves asimétricas](how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="f2964-117">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Asymmetric Keys](how-to-decrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 <span data-ttu-id="f2964-118">Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f2964-118">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>
  
### <a name="to-encrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="f2964-119">Para cifrar un elemento XML con una clave asimétrica</span><span class="sxs-lookup"><span data-stu-id="f2964-119">To encrypt an XML element with an asymmetric key</span></span>  
  
1. <span data-ttu-id="f2964-120">Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="f2964-120">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="f2964-121">Genere una clave simétrica mediante la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="f2964-121">Generate a symmetric key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="f2964-122">La clave se guarda automáticamente en el contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.</span><span class="sxs-lookup"><span data-stu-id="f2964-122">The key is automatically saved to the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="f2964-123">Esta clave se usará para cifrar la clave de sesión AES y se puede recuperar más adelante para descifrarla.</span><span class="sxs-lookup"><span data-stu-id="f2964-123">This key will be used to encrypt the AES session key and can be retrieved later to decrypt it.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="f2964-124">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="f2964-124">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="f2964-125">El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a cifrar.</span><span class="sxs-lookup"><span data-stu-id="f2964-125">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="f2964-126">Busque el elemento especificado en el objeto <xref:System.Xml.XmlDocument> y cree un objeto <xref:System.Xml.XmlElement> nuevo para representar el elemento que desea cifrar.</span><span class="sxs-lookup"><span data-stu-id="f2964-126">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span> <span data-ttu-id="f2964-127">En este ejemplo, el elemento `"creditcard"` está cifrado.</span><span class="sxs-lookup"><span data-stu-id="f2964-127">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="f2964-128">Cree una nueva sesión de clave mediante la clase <xref:System.Security.Cryptography.Aes>.</span><span class="sxs-lookup"><span data-stu-id="f2964-128">Create a new session key using the <xref:System.Security.Cryptography.Aes> class.</span></span>  <span data-ttu-id="f2964-129">Esta clave cifrará el elemento XML, se cifrará ella misma y se colocará en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2964-129">This key will encrypt the XML element, and then be encrypted itself and placed in the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="f2964-130">Cree una nueva instancia de la clase <xref:System.Security.Cryptography.Xml.EncryptedXml> y úsela para cifrar el elemento especificado mediante la clave de sesión.</span><span class="sxs-lookup"><span data-stu-id="f2964-130">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the session key.</span></span>  <span data-ttu-id="f2964-131">El método <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> devuelve el elemento cifrado como una matriz de bytes cifrados.</span><span class="sxs-lookup"><span data-stu-id="f2964-131">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="f2964-132">Construya un objeto <xref:System.Security.Cryptography.Xml.EncryptedData> y rellénelo con el identificador de dirección URL del elemento XML cifrado.</span><span class="sxs-lookup"><span data-stu-id="f2964-132">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the encrypted XML element.</span></span>  <span data-ttu-id="f2964-133">Este identificador de dirección URL permite que una entidad descifradora sepa que el código XML contiene un elemento cifrado.</span><span class="sxs-lookup"><span data-stu-id="f2964-133">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="f2964-134">Puede usar el campo <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> para especificar el identificador de dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f2964-134">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  <span data-ttu-id="f2964-135">El elemento XML de texto simple se reemplazará por un `EncryptedData` elemento <> encapsulado por este <xref:System.Security.Cryptography.Xml.EncryptedData> objeto.</span><span class="sxs-lookup"><span data-stu-id="f2964-135">The plaintext XML element will be replaced by an <`EncryptedData`> element encapsulated by this <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="f2964-136">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptionMethod> inicializado en el identificador de dirección URL del algoritmo criptográfico usado para generar la clave de sesión.</span><span class="sxs-lookup"><span data-stu-id="f2964-136">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the session key.</span></span>  <span data-ttu-id="f2964-137">Pase el objeto <xref:System.Security.Cryptography.Xml.EncryptionMethod> a la propiedad <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2964-137">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#9)]  
  
9. <span data-ttu-id="f2964-138">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedKey> para incluir la clave de sesión cifrada.</span><span class="sxs-lookup"><span data-stu-id="f2964-138">Create an <xref:System.Security.Cryptography.Xml.EncryptedKey> object to contain the encrypted session key.</span></span>  <span data-ttu-id="f2964-139">Cifre la clave de sesión, agréguela al objeto <xref:System.Security.Cryptography.Xml.EncryptedKey> y escriba un nombre de clave de sesión y una dirección URL de identificador de clave.</span><span class="sxs-lookup"><span data-stu-id="f2964-139">Encrypt the session key, add it to the <xref:System.Security.Cryptography.Xml.EncryptedKey> object, and enter a session key name and key identifier URL.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#10)]  
  
10. <span data-ttu-id="f2964-140">Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.DataReference> que asigne los datos cifrados a una clave de sesión determinada.</span><span class="sxs-lookup"><span data-stu-id="f2964-140">Create a new <xref:System.Security.Cryptography.Xml.DataReference> object that maps the encrypted data to a particular session key.</span></span>  <span data-ttu-id="f2964-141">Este paso opcional le permite especificar fácilmente que una clave única cifró varias partes de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2964-141">This optional step allows you to easily specify that multiple parts of an XML document were encrypted by a single key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#11)]  
  
11. <span data-ttu-id="f2964-142">Agregue la clave cifrada al objeto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="f2964-142">Add the encrypted key to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#12)]  
  
12. <span data-ttu-id="f2964-143">Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.KeyInfo> para especificar el nombre de la clave RSA.</span><span class="sxs-lookup"><span data-stu-id="f2964-143">Create a new <xref:System.Security.Cryptography.Xml.KeyInfo> object to specify the name of the RSA key.</span></span>  <span data-ttu-id="f2964-144">Agréguelo al objeto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="f2964-144">Add it to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span> <span data-ttu-id="f2964-145">Así, la entidad descifradora podrá identificar la clave asimétrica que debe usar al descifrar la clave de sesión.</span><span class="sxs-lookup"><span data-stu-id="f2964-145">This helps the decrypting party identify the correct asymmetric key to use when decrypting the session key.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#13)]  
  
13. <span data-ttu-id="f2964-146">Agregue los datos de elementos cifrados al objeto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="f2964-146">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#14)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#14)]  
  
14. <span data-ttu-id="f2964-147">Reemplace el elemento del objeto <xref:System.Xml.XmlDocument> original por el elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="f2964-147">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#15)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#15)]  
  
15. <span data-ttu-id="f2964-148">Guarde el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="f2964-148">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#16)]
     [!code-vb[HowToEncryptXMLElementAsymmetric#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="f2964-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2964-149">Example</span></span>  

 <span data-ttu-id="f2964-150">En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="f2964-150">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="f2964-151">También se supone que `"test.xml"` contiene un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="f2964-151">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="f2964-152">Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f2964-152">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f2964-153">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f2964-153">Compiling the Code</span></span>  
  
- <span data-ttu-id="f2964-154">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="f2964-154">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="f2964-155">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="f2964-155">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="f2964-156">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="f2964-156">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="f2964-157">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="f2964-157">.NET Security</span></span>

<span data-ttu-id="f2964-158">No almacene nunca una clave criptográfica simétrica en texto sin formato ni transfiera una clave simétrica entre equipos en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="f2964-158">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="f2964-159">Tampoco debe almacenar ni transferir nunca la clave privada de un par de claves asimétricas en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="f2964-159">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="f2964-160">Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md).</span><span class="sxs-lookup"><span data-stu-id="f2964-160">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](generating-keys-for-encryption-and-decryption.md).</span></span>  
  
<span data-ttu-id="f2964-161">No inserte nunca una clave directamente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="f2964-161">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="f2964-162">Las claves incrustadas se pueden leer fácilmente desde un ensamblado mediante el [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="f2964-162">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
<span data-ttu-id="f2964-163">Cuando termine de usar una clave criptográfica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.</span><span class="sxs-lookup"><span data-stu-id="f2964-163">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="f2964-164">A veces, las claves criptográficas se pueden leer desde la memoria con un depurador o desde un disco duro si la ubicación de memoria se pagina en el disco.</span><span class="sxs-lookup"><span data-stu-id="f2964-164">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2964-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2964-165">See also</span></span>

- [<span data-ttu-id="f2964-166">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="f2964-166">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="f2964-167">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="f2964-167">Cryptographic Services</span></span>](cryptographic-services.md)
- <span data-ttu-id="f2964-168">[Criptografía multiplataforma](cross-platform-cryptography.md)- <xref:System.Security.Cryptography.Xml></span><span class="sxs-lookup"><span data-stu-id="f2964-168">[Cross-Platform Cryptography](cross-platform-cryptography.md)- <xref:System.Security.Cryptography.Xml></span></span>
- [<span data-ttu-id="f2964-169">Descifrar elementos XML con claves asimétricas</span><span class="sxs-lookup"><span data-stu-id="f2964-169">How to: Decrypt XML Elements with Asymmetric Keys</span></span>](how-to-decrypt-xml-elements-with-asymmetric-keys.md)
- [<span data-ttu-id="f2964-170">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="f2964-170">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
