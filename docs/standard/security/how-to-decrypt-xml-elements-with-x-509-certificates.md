---
title: Procedimiento para descifrar elementos XML con certificados X.509
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- decryption
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: bd015722-d88d-408d-8ca8-e4e475c441ed
ms.openlocfilehash: 02a4a4ada6dcc242a96d630699797f2ea76987e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820285"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="eec98-102">Procedimiento para descifrar elementos XML con certificados X.509</span><span class="sxs-lookup"><span data-stu-id="eec98-102">How to: Decrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="eec98-103">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar y descifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="eec98-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="eec98-104">El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.</span><span class="sxs-lookup"><span data-stu-id="eec98-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="eec98-105">Para obtener más información sobre el estándar de cifrado XML, consulte la especificación de World Wide Web Consortium (W3C) para el cifrado XML ubicado en <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="eec98-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="eec98-106">En este ejemplo se descifra un elemento XML cifrado mediante los métodos descritos en: [Cómo: cifrar elementos XML con certificados X. 509](how-to-encrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="eec98-106">This example decrypts an XML element that was encrypted using the methods described in: [How to: Encrypt XML Elements with X.509 Certificates](how-to-encrypt-xml-elements-with-x-509-certificates.md).</span></span>  <span data-ttu-id="eec98-107">Busca un elemento de `EncryptedData`> de <, descifra el elemento y, a continuación, reemplaza el elemento por el elemento XML de texto sin formato original.</span><span class="sxs-lookup"><span data-stu-id="eec98-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
<span data-ttu-id="eec98-108">El ejemplo de código de este procedimiento descifra un elemento XML mediante un certificado X.509 del almacén de certificados local de la cuenta de usuario actual.</span><span class="sxs-lookup"><span data-stu-id="eec98-108">The code example in this procedure decrypts an XML element using an X.509 certificate from the local certificate store of the current user account.</span></span>  <span data-ttu-id="eec98-109">En el ejemplo se usa el <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> método para recuperar automáticamente el certificado X. 509 y descifrar una clave de sesión almacenada en el `EncryptedKey` elemento <> del `EncryptedData` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="eec98-109">The example uses the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to automatically retrieve the X.509 certificate and decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="eec98-110">Luego, el método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> usa automáticamente la clave de sesión para descifrar el elemento XML.</span><span class="sxs-lookup"><span data-stu-id="eec98-110">The <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method then automatically uses the session key to decrypt the XML element.</span></span>  
  
<span data-ttu-id="eec98-111">Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="eec98-111">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="eec98-112">Para descifrar un elemento XML con un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="eec98-112">To decrypt an XML element with an X.509 certificate</span></span>  
  
1. <span data-ttu-id="eec98-113">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="eec98-113">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="eec98-114">El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a descifrar.</span><span class="sxs-lookup"><span data-stu-id="eec98-114">The <xref:System.Xml.XmlDocument> object contains the XML element to decrypt.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. <span data-ttu-id="eec98-115">Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> nuevo pasando el objeto <xref:System.Xml.XmlDocument> al constructor.</span><span class="sxs-lookup"><span data-stu-id="eec98-115">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object by passing the <xref:System.Xml.XmlDocument> object to the constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. <span data-ttu-id="eec98-116">Descifre el documento XML mediante el método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>.</span><span class="sxs-lookup"><span data-stu-id="eec98-116">Decrypt the XML document using the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. <span data-ttu-id="eec98-117">Guarde el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="eec98-117">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="eec98-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eec98-118">Example</span></span>

<span data-ttu-id="eec98-119">En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="eec98-119">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="eec98-120">También se supone que `"test.xml"` contiene un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="eec98-120">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="eec98-121">Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eec98-121">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
[!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eec98-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="eec98-122">Compiling the Code</span></span>  
  
- <span data-ttu-id="eec98-123">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="eec98-123">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="eec98-124">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="eec98-124">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>

- <span data-ttu-id="eec98-125">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="eec98-125">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="eec98-126">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="eec98-126">.NET Security</span></span>

<span data-ttu-id="eec98-127">El certificado X.509 usado en este ejemplo se usa únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="eec98-127">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="eec98-128">Las aplicaciones deben usar un certificado X. 509 generado por una entidad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="eec98-128">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec98-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="eec98-129">See also</span></span>

- [<span data-ttu-id="eec98-130">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="eec98-130">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="eec98-131">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="eec98-131">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="eec98-132">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="eec98-132">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="eec98-133">Procedimiento para cifrar elementos XML con certificados X.509</span><span class="sxs-lookup"><span data-stu-id="eec98-133">How to: Encrypt XML Elements with X.509 Certificates</span></span>](how-to-encrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="eec98-134">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="eec98-134">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
