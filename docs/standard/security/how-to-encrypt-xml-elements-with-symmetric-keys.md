---
title: Procedimiento para cifrar elementos XML con claves simétricas
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AES algorithm
- cryptography [.NET], symmetric keys
- encryption [.NET], symmetric keys
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.Aes class
- XML encryption
- Advanced Encryption Standard algorithm
ms.assetid: d8461a44-aa2c-4ef4-b3e4-ab7cbaaee1b5
ms.openlocfilehash: dd69ec6a5317f7f6f800cd225d920a1934c77a0c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555818"
---
# <a name="how-to-encrypt-xml-elements-with-symmetric-keys"></a><span data-ttu-id="301c7-102">Procedimiento para cifrar elementos XML con claves simétricas</span><span class="sxs-lookup"><span data-stu-id="301c7-102">How to: Encrypt XML Elements with Symmetric Keys</span></span>

<span data-ttu-id="301c7-103">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="301c7-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="301c7-104">El cifrado XML le permite almacenar o transportar información XML confidencial, sin preocuparse de que los datos se puedan leer con facilidad.</span><span class="sxs-lookup"><span data-stu-id="301c7-104">XML Encryption allows you to store or transport sensitive XML, without worrying about the data being easily read.</span></span>  <span data-ttu-id="301c7-105">Este procedimiento cifra un elemento XML mediante el algoritmo de Estándar de cifrado avanzado (AES).</span><span class="sxs-lookup"><span data-stu-id="301c7-105">This procedure encrypts an XML element using the Advanced Encryption Standard (AES) algorithm.</span></span>  
  
 <span data-ttu-id="301c7-106">Para obtener información sobre cómo descifrar un elemento XML cifrado mediante este procedimiento, vea [Cómo: descifrar elementos XML con claves simétricas](how-to-decrypt-xml-elements-with-symmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="301c7-106">For information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with Symmetric Keys](how-to-decrypt-xml-elements-with-symmetric-keys.md).</span></span>  
  
 <span data-ttu-id="301c7-107">Al usar un algoritmo simétrico como AES para cifrar datos XML, debe usar la misma clave para cifrar y descifrar los datos XML.</span><span class="sxs-lookup"><span data-stu-id="301c7-107">When you use a symmetric algorithm like AES to encrypt XML data, you must use the same key to encrypt and decrypt the XML data.</span></span>  <span data-ttu-id="301c7-108">En el ejemplo de este procedimiento se supone que el código XML cifrado se descifrará con la misma clave y que las partes de cifrado y descifrado están de acuerdo en el algoritmo y la clave que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="301c7-108">The example in this procedure assumes that the encrypted XML will be decrypted using the same key, and that the encrypting and decrypting parties agree on the algorithm and key to use.</span></span>  <span data-ttu-id="301c7-109">En este ejemplo no se almacena ni se cifra la clave AES dentro del código XML cifrado.</span><span class="sxs-lookup"><span data-stu-id="301c7-109">This example does not store or encrypt the AES key within the encrypted XML.</span></span>  
  
 <span data-ttu-id="301c7-110">Este ejemplo es idóneo en las situaciones en las que una aplicación necesita cifrar datos en función de una clave de sesión almacenada en memoria o en función de una clave criptográficamente segura derivada de una contraseña.</span><span class="sxs-lookup"><span data-stu-id="301c7-110">This example is appropriate for situations where a single application needs to encrypt data based on a session key stored in memory, or based on a cryptographically strong key derived from a password.</span></span>  <span data-ttu-id="301c7-111">En las situaciones en las que dos o más aplicaciones deben compartir datos XML cifrados, considere el uso de un esquema de cifrado basado en un algoritmo asimétrico o un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="301c7-111">For situations where two or more applications need to share encrypted XML data, consider using an encryption scheme based on an asymmetric algorithm or an X.509 certificate.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-a-symmetric-key"></a><span data-ttu-id="301c7-112">Para cifrar un elemento XML con una clave simétrica</span><span class="sxs-lookup"><span data-stu-id="301c7-112">To encrypt an XML element with a symmetric key</span></span>  
  
1. <span data-ttu-id="301c7-113">Genere una clave simétrica mediante la clase <xref:System.Security.Cryptography.Aes>.</span><span class="sxs-lookup"><span data-stu-id="301c7-113">Generate a symmetric key using the <xref:System.Security.Cryptography.Aes> class.</span></span>  <span data-ttu-id="301c7-114">Esta clave se usará para cifrar el elemento XML.</span><span class="sxs-lookup"><span data-stu-id="301c7-114">This key will be used to encrypt the XML element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementSymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#2)]  
  
2. <span data-ttu-id="301c7-115">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="301c7-115">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="301c7-116">El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a cifrar.</span><span class="sxs-lookup"><span data-stu-id="301c7-116">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementSymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#3)]  
  
3. <span data-ttu-id="301c7-117">Busque el elemento especificado en el objeto <xref:System.Xml.XmlDocument> y cree un objeto <xref:System.Xml.XmlElement> nuevo para representar el elemento que desea cifrar.</span><span class="sxs-lookup"><span data-stu-id="301c7-117">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="301c7-118">En este ejemplo, el elemento `"creditcard"` está cifrado.</span><span class="sxs-lookup"><span data-stu-id="301c7-118">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementSymmetric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#4)]  
  
4. <span data-ttu-id="301c7-119">Cree una nueva instancia de la clase <xref:System.Security.Cryptography.Xml.EncryptedXml> y úsela para cifrar el <xref:System.Xml.XmlElement> con la clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="301c7-119">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the <xref:System.Xml.XmlElement> with the symmetric key.</span></span>  <span data-ttu-id="301c7-120">El método <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> devuelve el elemento cifrado como una matriz de bytes cifrados.</span><span class="sxs-lookup"><span data-stu-id="301c7-120">The <xref:System.Security.Cryptography.Xml.EncryptedXml.EncryptData%2A> method returns the encrypted element as an array of encrypted bytes.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementSymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#5)]  
  
5. <span data-ttu-id="301c7-121">Construya un objeto <xref:System.Security.Cryptography.Xml.EncryptedData> y rellénelo con el identificador de dirección URL del elemento XML cifrado.</span><span class="sxs-lookup"><span data-stu-id="301c7-121">Construct an <xref:System.Security.Cryptography.Xml.EncryptedData> object and populate it with the URL identifier of the XML Encryption element.</span></span>  <span data-ttu-id="301c7-122">Este identificador de dirección URL permite que una entidad descifradora sepa que el código XML contiene un elemento cifrado.</span><span class="sxs-lookup"><span data-stu-id="301c7-122">This URL identifier lets a decrypting party know that the XML contains an encrypted element.</span></span>  <span data-ttu-id="301c7-123">Puede usar el campo <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> para especificar el identificador de dirección URL.</span><span class="sxs-lookup"><span data-stu-id="301c7-123">You can use the <xref:System.Security.Cryptography.Xml.EncryptedXml.XmlEncElementUrl> field to specify the URL identifier.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementSymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#6)]  
  
6. <span data-ttu-id="301c7-124">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptionMethod> inicializado en el identificador de dirección URL del algoritmo criptográfico usado para generar la clave.</span><span class="sxs-lookup"><span data-stu-id="301c7-124">Create an <xref:System.Security.Cryptography.Xml.EncryptionMethod> object that is initialized to the URL identifier of the cryptographic algorithm used to generate the key.</span></span>  <span data-ttu-id="301c7-125">Pase el objeto <xref:System.Security.Cryptography.Xml.EncryptionMethod> a la propiedad <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A>.</span><span class="sxs-lookup"><span data-stu-id="301c7-125">Pass the <xref:System.Security.Cryptography.Xml.EncryptionMethod> object to the <xref:System.Security.Cryptography.Xml.EncryptedType.EncryptionMethod%2A> property.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementSymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#7)]  
  
7. <span data-ttu-id="301c7-126">Agregue los datos de elementos cifrados al objeto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="301c7-126">Add the encrypted element data to the <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementSymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#8)]  
  
8. <span data-ttu-id="301c7-127">Reemplace el elemento del objeto <xref:System.Xml.XmlDocument> original por el elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="301c7-127">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementSymmetric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="301c7-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="301c7-128">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="301c7-129">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="301c7-129">Compiling the Code</span></span>  
  
- <span data-ttu-id="301c7-130">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="301c7-130">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="301c7-131">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="301c7-131">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="301c7-132">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="301c7-132">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="301c7-133">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="301c7-133">.NET Security</span></span>

<span data-ttu-id="301c7-134">No almacene nunca una clave criptográfica en texto sin formato ni transfiera una clave entre equipos en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="301c7-134">Never store a cryptographic key in plaintext or transfer a key between machines in plaintext.</span></span>  <span data-ttu-id="301c7-135">En su lugar, use un contenedor de claves seguro para almacenar las claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="301c7-135">Instead, use a secure key container to store cryptographic keys.</span></span>  
  
<span data-ttu-id="301c7-136">Cuando termine de usar una clave criptográfica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.</span><span class="sxs-lookup"><span data-stu-id="301c7-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301c7-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="301c7-137">See also</span></span>

- <span data-ttu-id="301c7-138">[Modelo de criptografía](cryptography-model.md) : describe cómo se implementa la criptografía en la biblioteca de clases base.</span><span class="sxs-lookup"><span data-stu-id="301c7-138">[Cryptography Model](cryptography-model.md) - Describes how cryptography is implemented in the base class library.</span></span>
- [<span data-ttu-id="301c7-139">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="301c7-139">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="301c7-140">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="301c7-140">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="301c7-141">Procedimiento para descifrar elementos XML con claves simétricas</span><span class="sxs-lookup"><span data-stu-id="301c7-141">How to: Decrypt XML Elements with Symmetric Keys</span></span>](how-to-decrypt-xml-elements-with-symmetric-keys.md)
- [<span data-ttu-id="301c7-142">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="301c7-142">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
