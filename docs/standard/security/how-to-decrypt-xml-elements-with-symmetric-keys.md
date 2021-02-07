---
description: 'Más información acerca de cómo: descifrar elementos XML con claves simétricas'
title: Procedimiento para descifrar elementos XML con claves simétricas
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.Aes class
- XML encryption
- decryption
ms.assetid: 6038aff0-f92c-4e29-a618-d793410410d8
ms.openlocfilehash: 894b202143daf2af767fd9877266e2323e0057e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685184"
---
# <a name="how-to-decrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="1395b-103">Procedimiento para descifrar elementos XML con claves simétricas</span><span class="sxs-lookup"><span data-stu-id="1395b-103">How to: Decrypt XML Elements with Symmetric Keys</span></span>

<span data-ttu-id="1395b-104">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="1395b-104">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="1395b-105">El cifrado XML le permite almacenar o transportar información XML confidencial, sin preocuparse de que los datos se puedan leer con facilidad.</span><span class="sxs-lookup"><span data-stu-id="1395b-105">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="1395b-106">En este ejemplo de código se descifra un elemento XML mediante el algoritmo Estándar de cifrado avanzado (AES).</span><span class="sxs-lookup"><span data-stu-id="1395b-106">This code example decrypts an XML element using the Advanced Encryption Standard (AES) algorithm.</span></span>
  
 <span data-ttu-id="1395b-107">Para obtener información sobre cómo cifrar un elemento XML mediante este procedimiento, vea [Cómo: cifrar elementos XML con claves simétricas](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="1395b-107">For information about how to encrypt an XML element using this procedure, see [How to: Encrypt XML Elements with Symmetric Keys](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="1395b-108">Al usar un algoritmo simétrico como AES para cifrar datos XML, debe usar la misma clave para cifrar y descifrar los datos XML.</span><span class="sxs-lookup"><span data-stu-id="1395b-108">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="1395b-109">En el ejemplo de este procedimiento se supone que el código XML cifrado se cifró con la misma clave y que las partes de cifrado y descifrado están de acuerdo en el algoritmo y la clave que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="1395b-109">The example in this procedure assumes that the encrypted XML was encrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="1395b-110">En este ejemplo no se almacena ni se cifra la clave AES dentro del código XML cifrado.</span><span class="sxs-lookup"><span data-stu-id="1395b-110">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="1395b-111">Este ejemplo es idóneo en las situaciones en las que una aplicación necesita cifrar datos en función de una clave de sesión almacenada en memoria o en función de una clave criptográficamente segura derivada de una contraseña.</span><span class="sxs-lookup"><span data-stu-id="1395b-111">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="1395b-112">En las situaciones en las que dos o más aplicaciones deben compartir datos XML cifrados, considere el uso de un esquema de cifrado basado en un algoritmo asimétrico o un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="1395b-112">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="1395b-113">Para descifrar un elemento XML con una clave simétrica</span><span class="sxs-lookup"><span data-stu-id="1395b-113">To decrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="1395b-114">Cifre un elemento XML con la clave generada anteriormente mediante las técnicas descritas en [Cómo: cifrar elementos XML con claves simétricas](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="1395b-114">Encrypt an XML element with the previously generated key using the techniques described in [How to: Encrypt XML Elements with Symmetric Keys](how-to-encrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
2. <span data-ttu-id="1395b-115">Busque el `EncryptedData` elemento <> (definido por el estándar de cifrado XML) en un <xref:System.Xml.XmlDocument> objeto que contenga el XML cifrado y cree un nuevo <xref:System.Xml.XmlElement> objeto para representar ese elemento.</span><span class="sxs-lookup"><span data-stu-id="1395b-115">Find the <`EncryptedData`> element (defined by the XML Encryption standard) in an <xref:System.Xml.XmlDocument> object that contains the encrypted XML and create a new <xref:System.Xml.XmlElement> object to represent that element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#10)]  
  
3. <span data-ttu-id="1395b-116">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedData> cargando los datos XML sin formato desde el objeto <xref:System.Xml.XmlElement> que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="1395b-116">Create an <xref:System.Security.Cryptography.Xml.EncryptedData> object by loading the raw XML data from the previously created <xref:System.Xml.XmlElement> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#11)]  
  
4. <span data-ttu-id="1395b-117">Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> y úselo para descifrar los datos XML usando la misma clave que se usó para el cifrado.</span><span class="sxs-lookup"><span data-stu-id="1395b-117">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object and use it to decrypt the XML data using the same key that was used for encryption.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#12)]  
  
5. <span data-ttu-id="1395b-118">Reemplace el elemento cifrado por el elemento de texto simple recién descifrado dentro del documento XML.</span><span class="sxs-lookup"><span data-stu-id="1395b-118">Replace the encrypted element with the newly decrypted plaintext element within the XML document.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="1395b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1395b-119">Example</span></span>  

 <span data-ttu-id="1395b-120">En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="1395b-120">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="1395b-121">También se supone que `"test.xml"` contiene un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="1395b-121">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="1395b-122">Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1395b-122">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1395b-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1395b-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="1395b-124">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="1395b-124">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="1395b-125">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="1395b-125">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="1395b-126">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="1395b-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="1395b-127">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="1395b-127">.NET Security</span></span>
  
<span data-ttu-id="1395b-128">No almacene nunca una clave criptográfica en texto sin formato ni transfiera una clave entre equipos en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="1395b-128">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  
  
<span data-ttu-id="1395b-129">Cuando haya terminado de usar una clave criptográfica simétrica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.</span><span class="sxs-lookup"><span data-stu-id="1395b-129">When you are done using a symmetric cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1395b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1395b-130">See also</span></span>

- [<span data-ttu-id="1395b-131">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="1395b-131">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="1395b-132">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="1395b-132">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="1395b-133">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="1395b-133">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="1395b-134">Procedimiento para cifrar elementos XML con claves simétricas</span><span class="sxs-lookup"><span data-stu-id="1395b-134">How to: Encrypt XML Elements with Symmetric Keys</span></span>](how-to-encrypt-xml-elements-with-symmetric-keys.md)
- [<span data-ttu-id="1395b-135">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="1395b-135">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
