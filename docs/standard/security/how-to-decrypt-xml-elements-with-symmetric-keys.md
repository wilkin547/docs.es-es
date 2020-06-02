---
title: Procedimiento para descifrar elementos XML con claves simétricas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- symmetric keys
- System.Security.Cryptography.EncryptedXml class
- System.Security.Cryptography.RijndaelManaged class
- XML encryption
- Rijndael
- decryption
ms.assetid: 6038aff0-f92c-4e29-a618-d793410410d8
ms.openlocfilehash: bb34332d345ee7bcb9037dc7bdf0deebbe70c3c9
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277432"
---
# <a name="how-to-decrypt-xml-elements-with-symmetric-keys"></a>Procedimiento para descifrar elementos XML con claves simétricas
Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar un elemento dentro de un documento XML.  El cifrado XML le permite almacenar o transportar información XML confidencial, sin preocuparse de que los datos se puedan leer con facilidad.  Este ejemplo de código descifra un elemento XML mediante el algoritmo AES (Estándar de cifrado avanzado), también conocido como Rijndael.  
  
 Para obtener información sobre cómo cifrar un elemento XML mediante este procedimiento, vea [Cómo: cifrar elementos XML con claves simétricas](how-to-encrypt-xml-elements-with-symmetric-keys.md).  
  
 Al usar un algoritmo simétrico como AES para cifrar datos XML, debe usar la misma clave para cifrar y descifrar los datos XML.  En el ejemplo de este procedimiento se supone que el código XML cifrado se cifró con la misma clave y que las partes de cifrado y descifrado están de acuerdo en el algoritmo y la clave que se van a usar.  En este ejemplo no se almacena ni se cifra la clave AES dentro del código XML cifrado.  
  
 Este ejemplo es idóneo en las situaciones en las que una aplicación necesita cifrar datos en función de una clave de sesión almacenada en memoria o en función de una clave criptográficamente segura derivada de una contraseña.  En las situaciones en las que dos o más aplicaciones deben compartir datos XML cifrados, considere el uso de un esquema de cifrado basado en un algoritmo asimétrico o un certificado X.509.  
  
### <a name="to-decrypt-an-xml-element-with-a-symmetric-key"></a>Para descifrar un elemento XML con una clave simétrica  
  
1. Cifre un elemento XML con la clave generada anteriormente mediante las técnicas descritas en [Cómo: cifrar elementos XML con claves simétricas](how-to-encrypt-xml-elements-with-symmetric-keys.md).  
  
2. Busque el `EncryptedData` elemento <> (definido por el estándar de cifrado XML) en un <xref:System.Xml.XmlDocument> objeto que contenga el XML cifrado y cree un nuevo <xref:System.Xml.XmlElement> objeto para representar ese elemento.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementSymmetric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#10)]  
  
3. Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedData> cargando los datos XML sin formato desde el objeto <xref:System.Xml.XmlElement> que se creó previamente.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementSymmetric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#11)]  
  
4. Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> y úselo para descifrar los datos XML usando la misma clave que se usó para el cifrado.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#12)]
     [!code-vb[HowToEncryptXMLElementSymmetric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#12)]  
  
5. Reemplace el elemento cifrado por el elemento de texto simple recién descifrado dentro del documento XML.  
  
     [!code-csharp[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#13)]
     [!code-vb[HowToEncryptXMLElementSymmetric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#13)]  
  
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
  
 [!code-csharp[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementSymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementSymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Para compilar este ejemplo, debe incluir una referencia a `System.Security.dll`.  
  
- Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No almacene nunca una clave criptográfica en texto sin formato ni transfiera una clave entre equipos en texto sin formato.  
  
 Cuando haya terminado de usar una clave criptográfica simétrica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Security.Cryptography.Xml>
- [Procedimiento para cifrar elementos XML con claves simétricas](how-to-encrypt-xml-elements-with-symmetric-keys.md)
