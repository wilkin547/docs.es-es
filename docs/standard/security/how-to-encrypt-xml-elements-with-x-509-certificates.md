---
description: 'Más información acerca de cómo: cifrar elementos XML con certificados X. 509'
title: Procedimiento para cifrar elementos XML con certificados X.509
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], X.509 certificates
- cryptography [.NET], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: f815d253b15823070e074c5d922d3024da602a0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685106"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="11110-103">Procedimiento para cifrar elementos XML con certificados X.509</span><span class="sxs-lookup"><span data-stu-id="11110-103">How to: Encrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="11110-104">Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar un elemento dentro de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="11110-104">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="11110-105">El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.</span><span class="sxs-lookup"><span data-stu-id="11110-105">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="11110-106">Para obtener más información sobre el estándar de cifrado XML, consulte la especificación de World Wide Web Consortium (W3C) para el cifrado XML ubicado en <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="11110-106">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="11110-107">Puede usar el cifrado de XML para reemplazar cualquier elemento o documento XML con un elemento <`EncryptedData`> que contenga los datos XML cifrados.</span><span class="sxs-lookup"><span data-stu-id="11110-107">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="11110-108">El elemento <`EncryptedData`> puede contener subelementos con información sobre las claves y los procesos usados durante el cifrado.</span><span class="sxs-lookup"><span data-stu-id="11110-108">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="11110-109">El cifrado XML permite que un documento contenga varios elementos cifrados y permite cifrar varias veces un elemento.</span><span class="sxs-lookup"><span data-stu-id="11110-109">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="11110-110">El ejemplo de código de este procedimiento muestra cómo crear un elemento <`EncryptedData`> junto con otros subelementos que se pueden usar posteriormente durante el descifrado.</span><span class="sxs-lookup"><span data-stu-id="11110-110">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
<span data-ttu-id="11110-111">En este ejemplo se cifra un elemento XML mediante dos claves.</span><span class="sxs-lookup"><span data-stu-id="11110-111">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="11110-112">En el ejemplo se recupera mediante programación un certificado y se utiliza para cifrar un elemento XML mediante el <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> método.</span><span class="sxs-lookup"><span data-stu-id="11110-112">The example programmatically retrieves a certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="11110-113">Internamente, el método <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> crea una clave de sesión independiente y la usa para cifrar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="11110-113">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="11110-114">Este método cifra la clave de sesión y la guarda junto con el XML cifrado dentro de un nuevo elemento <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="11110-114">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  

<span data-ttu-id="11110-115">Para descifrar el elemento XML, llame al <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> método, que recupera automáticamente el certificado X. 509 del almacén y realiza el descifrado necesario.</span><span class="sxs-lookup"><span data-stu-id="11110-115">To decrypt the XML element, call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="11110-116">Para más información sobre la manera de descifrar un elemento XML cifrado mediante este procedimiento, vea [Cómo: Descifrar elementos XML con certificados X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="11110-116">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
<span data-ttu-id="11110-117">Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="11110-117">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="11110-118">Para cifrar un elemento XML con un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="11110-118">To encrypt an XML element with an X.509 certificate</span></span>  

<span data-ttu-id="11110-119">Para ejecutar este ejemplo, debe crear un certificado de prueba y guardarlo en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="11110-119">To run this example, you need to create a test certificate and save it in a certificate store.</span></span> <span data-ttu-id="11110-120">Las instrucciones para esa tarea solo se proporcionan para la [herramienta de creación de certificados de Windows (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="11110-120">Instructions for that task are provided only for the Windows [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span></span>

1. <span data-ttu-id="11110-121">Utilice [Makecert.exe](/windows/desktop/SecCrypto/makecert) para generar un certificado X. 509 de prueba y colocarlo en el almacén de usuario local.</span><span class="sxs-lookup"><span data-stu-id="11110-121">Use [Makecert.exe](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="11110-122">Debe generar una clave de intercambio y debe hacerla exportable.</span><span class="sxs-lookup"><span data-stu-id="11110-122">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="11110-123">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="11110-123">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="11110-124">Cree un objeto <xref:System.Security.Cryptography.X509Certificates.X509Store> e inicialícelo para abrir el almacén del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="11110-124">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="11110-125">Abra el almacén en modo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="11110-125">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="11110-126">Inicialice una <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> con todos los certificados del almacén.</span><span class="sxs-lookup"><span data-stu-id="11110-126">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="11110-127">Enumere los certificados del almacén y busque el certificado con el nombre adecuado.</span><span class="sxs-lookup"><span data-stu-id="11110-127">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="11110-128">En este ejemplo, el certificado se llama  `"CN=XML_ENC_TEST_CERT"`.</span><span class="sxs-lookup"><span data-stu-id="11110-128">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="11110-129">Cierre el almacén después de localizar el certificado.</span><span class="sxs-lookup"><span data-stu-id="11110-129">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="11110-130">Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.</span><span class="sxs-lookup"><span data-stu-id="11110-130">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="11110-131">El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a cifrar.</span><span class="sxs-lookup"><span data-stu-id="11110-131">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="11110-132">Busque el elemento especificado en el objeto <xref:System.Xml.XmlDocument> y cree un objeto <xref:System.Xml.XmlElement> nuevo para representar el elemento que desea cifrar.</span><span class="sxs-lookup"><span data-stu-id="11110-132">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="11110-133">En este ejemplo, el elemento `"creditcard"` está cifrado.</span><span class="sxs-lookup"><span data-stu-id="11110-133">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="11110-134">Cree una nueva instancia de la clase <xref:System.Security.Cryptography.Xml.EncryptedXml> y úsela para cifrar el elemento especificado mediante el certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="11110-134">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="11110-135">El método <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> devuelve el elemento cifrado como un objeto <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="11110-135">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="11110-136">Reemplace el elemento del objeto <xref:System.Xml.XmlDocument> original por el elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="11110-136">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="11110-137">Guarde el objeto <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="11110-137">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="11110-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11110-138">Example</span></span>  

 <span data-ttu-id="11110-139">En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="11110-139">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="11110-140">También se supone que `"test.xml"` contiene un elemento `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="11110-140">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="11110-141">Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="11110-141">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11110-142">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="11110-142">Compiling the Code</span></span>  
  
- <span data-ttu-id="11110-143">En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="11110-143">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="11110-144">En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="11110-144">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="11110-145">Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="11110-145">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="11110-146">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="11110-146">.NET Security</span></span>
  
<span data-ttu-id="11110-147">El certificado X.509 usado en este ejemplo se usa únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="11110-147">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="11110-148">Las aplicaciones deben usar un certificado X. 509 generado por una entidad de certificación de confianza.</span><span class="sxs-lookup"><span data-stu-id="11110-148">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11110-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="11110-149">See also</span></span>

- [<span data-ttu-id="11110-150">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="11110-150">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="11110-151">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="11110-151">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="11110-152">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="11110-152">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="11110-153">Procedimiento para descifrar elementos XML con certificados X.509</span><span class="sxs-lookup"><span data-stu-id="11110-153">How to: Decrypt XML Elements with X.509 Certificates</span></span>](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="11110-154">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="11110-154">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
