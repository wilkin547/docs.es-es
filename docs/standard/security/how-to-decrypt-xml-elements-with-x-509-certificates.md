---
title: 'Cómo: Descifrar elementos XML con certificados X.509'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 46fbefbf7a427ec0d60a34ecc2166f8499d08575
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708893"
---
# <a name="how-to-decrypt-xml-elements-with-x509-certificates"></a>Cómo: Descifrar elementos XML con certificados X.509
Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar y descifrar un elemento dentro de un documento XML.  El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.  Para obtener más información sobre el estándar de cifrado XML, consulte la especificación de World Wide Web Consortium (W3C) para el cifrado XML ubicado en <https://www.w3.org/TR/xmldsig-core/>.  
  
 En este ejemplo se descifra un elemento XML cifrado mediante los métodos descritos en: [Cómo: cifrar elementos XML con certificados X. 509](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md).  Busca un <`EncryptedData`elemento >, descifra el elemento y, a continuación, reemplaza el elemento por el elemento XML de texto sin formato original.  
  
 El ejemplo de código de este procedimiento descifra un elemento XML mediante un certificado X.509 del almacén de certificados local de la cuenta de usuario actual.  En el ejemplo se usa el método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> para recuperar automáticamente el certificado X. 509 y descifrar una clave de sesión almacenada en el <`EncryptedKey`elemento > del elemento <`EncryptedData`>.  Luego, el método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> usa automáticamente la clave de sesión para descifrar el elemento XML.  
  
 Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.  
  
### <a name="to-decrypt-an-xml-element-with-an-x509-certificate"></a>Para descifrar un elemento XML con un certificado X.509  
  
1. Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.  El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a descifrar.  
  
     [!code-csharp[HowToDecryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#2)]  
  
2. Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> nuevo pasando el objeto <xref:System.Xml.XmlDocument> al constructor.  
  
     [!code-csharp[HowToDecryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#3)]  
  
3. Descifre el documento XML mediante el método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A>.  
  
     [!code-csharp[HowToDecryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToDecryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#4)]  
  
4. Guarde el objeto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToDecryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#5)]  
  
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
  
 [!code-csharp[HowToDecryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Para compilar este ejemplo, debe incluir una referencia a `System.Security.dll`.  
  
- Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 El certificado X.509 usado en este ejemplo se usa únicamente para pruebas.  Las aplicaciones deben usar un certificado X.509 generado por una entidad de certificación de confianza o un certificado generado por Microsoft Windows Certificate Server.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Cryptography.Xml>
- [Cifrar elementos XML con certificados X.509](../../../docs/standard/security/how-to-encrypt-xml-elements-with-x-509-certificates.md)
