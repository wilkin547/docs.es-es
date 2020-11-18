---
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
ms.openlocfilehash: 5007404c1e6e872c169ce7ce71425f14d20d3a25
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820194"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a>Procedimiento para cifrar elementos XML con certificados X.509

Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar un elemento dentro de un documento XML.  El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.  Para obtener más información sobre el estándar de cifrado XML, consulte la especificación de World Wide Web Consortium (W3C) para el cifrado XML ubicado en <https://www.w3.org/TR/xmldsig-core/> .  
  
 Puede usar el cifrado de XML para reemplazar cualquier elemento o documento XML con un elemento <`EncryptedData`> que contenga los datos XML cifrados. El elemento <`EncryptedData`> puede contener subelementos con información sobre las claves y los procesos usados durante el cifrado.  El cifrado XML permite que un documento contenga varios elementos cifrados y permite cifrar varias veces un elemento.  El ejemplo de código de este procedimiento muestra cómo crear un elemento <`EncryptedData`> junto con otros subelementos que se pueden usar posteriormente durante el descifrado.  
  
En este ejemplo se cifra un elemento XML mediante dos claves. En el ejemplo se recupera mediante programación un certificado y se utiliza para cifrar un elemento XML mediante el <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> método. Internamente, el método <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> crea una clave de sesión independiente y la usa para cifrar el documento XML. Este método cifra la clave de sesión y la guarda junto con el XML cifrado dentro de un nuevo elemento <`EncryptedData`>.  

Para descifrar el elemento XML, llame al <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> método, que recupera automáticamente el certificado X. 509 del almacén y realiza el descifrado necesario.  Para más información sobre la manera de descifrar un elemento XML cifrado mediante este procedimiento, vea [Cómo: Descifrar elementos XML con certificados X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md).  
  
Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a>Para cifrar un elemento XML con un certificado X.509  

Para ejecutar este ejemplo, debe crear un certificado de prueba y guardarlo en un almacén de certificados. Las instrucciones para esa tarea solo se proporcionan para la [herramienta de creación de certificados de Windows (Makecert.exe)](/windows/desktop/SecCrypto/makecert).

1. Utilice [Makecert.exe](/windows/desktop/SecCrypto/makecert) para generar un certificado X. 509 de prueba y colocarlo en el almacén de usuario local. Debe generar una clave de intercambio y debe hacerla exportable. Ejecute el siguiente comando:  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. Cree un objeto <xref:System.Security.Cryptography.X509Certificates.X509Store> e inicialícelo para abrir el almacén del usuario actual.  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. Abra el almacén en modo de solo lectura.  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. Inicialice una <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> con todos los certificados del almacén.  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. Enumere los certificados del almacén y busque el certificado con el nombre adecuado.  En este ejemplo, el certificado se llama  `"CN=XML_ENC_TEST_CERT"`.  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. Cierre el almacén después de localizar el certificado.  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.  El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a cifrar.  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. Busque el elemento especificado en el objeto <xref:System.Xml.XmlDocument> y cree un objeto <xref:System.Xml.XmlElement> nuevo para representar el elemento que desea cifrar.  En este ejemplo, el elemento `"creditcard"` está cifrado.  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. Cree una nueva instancia de la clase <xref:System.Security.Cryptography.Xml.EncryptedXml> y úsela para cifrar el elemento especificado mediante el certificado X.509.  El método <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> devuelve el elemento cifrado como un objeto <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. Reemplace el elemento del objeto <xref:System.Xml.XmlDocument> original por el elemento <xref:System.Security.Cryptography.Xml.EncryptedData>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. Guarde el objeto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se supone que un archivo llamado `"test.xml"` se encuentra en el mismo directorio que el programa compilado.  También se supone que `"test.xml"` contiene un elemento `"creditcard"`.  Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .

- En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).
  
- Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-security"></a>Seguridad de .NET
  
El certificado X.509 usado en este ejemplo se usa únicamente para pruebas.  Las aplicaciones deben usar un certificado X. 509 generado por una entidad de certificación de confianza.  
  
## <a name="see-also"></a>Vea también

- [Modelo de criptografía](cryptography-model.md)
- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [Procedimiento para descifrar elementos XML con certificados X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
