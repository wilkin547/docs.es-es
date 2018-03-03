---
title: "Cómo: Descifrar elementos XML con claves asimétricas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 698a542765cf8599a2f07e747669893502b75045
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Cómo: Descifrar elementos XML con claves asimétricas
Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar y descifrar un elemento dentro de un documento XML.  El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.  Para obtener más información acerca del estándar de cifrado XML, vea la recomendación de World Wide Web Consortium (W3C) [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).  
  
 El ejemplo de este procedimiento descifra un elemento XML que se cifró mediante los métodos descritos en [Cómo: cifrar elementos XML con claves asimétricas](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  Busca un elemento <`EncryptedData`>, lo descifra y lo reemplaza por el elemento XML de texto sin formato original.  
  
 En este ejemplo se descifra un elemento XML mediante dos claves.  Recupera de un contenedor de claves una clave privada RSA generada previamente y la usa para descifrar una clave de sesión almacenada en el elemento <`EncryptedKey`> del elemento <`EncryptedData`>.  Luego, el ejemplo usa la clave de sesión para descifrar el elemento XML.  
  
 Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>Para descifrar un elemento XML con una clave asimétrica  
  
1.  Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2.  Recupere una clave asimétrica previamente generada desde el contenedor mediante el objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  La clave se recupera automáticamente del contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3.  Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> nuevo para descifrar el documento.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4.  Agregue una asignación de clave/nombre para asociar la clave RSA al elemento del documento que se debe descifrar.  Debe usar el mismo nombre para la clave que usó al cifrar el documento.  Tenga en cuenta que este nombre es independiente del que haya usado para identificar la clave en el contenedor de claves especificado en el paso 1.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5.  Llame al método <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> para descifrar el elemento <`EncryptedData`>.  Este método usa la clave RSA para descifrar la clave de sesión y la usa automáticamente para descifrar el elemento XML.  También reemplaza automáticamente el elemento <`EncryptedData`> por el texto sin formato original.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6.  Guarde el documento XML.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se supone que un archivo llamado `test.xml` se encuentra en el mismo directorio que el programa compilado.  También se supone que `test.xml` contiene un elemento XML que se cifró mediante las técnicas descritas en [Cómo: cifrar elementos XML con claves asimétricas](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Para compilar este ejemplo, debe incluir una referencia a `System.Security.dll`.  
  
-   Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 No almacene nunca una clave criptográfica simétrica en texto sin formato ni transfiera una clave simétrica entre equipos en texto sin formato.  Tampoco debe almacenar ni transferir nunca la clave privada de un par de claves asimétricas en texto sin formato.  Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 No inserte nunca una clave directamente en el código fuente.  Las claves insertadas se pueden leer fácilmente desde un ensamblado mediante el uso de [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como Bloc de notas.  
  
 Cuando termine de usar una clave criptográfica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.  A veces, las claves criptográficas se pueden leer desde la memoria con un depurador o desde un disco duro si la ubicación de memoria se pagina en el disco.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Cryptography.Xml>  
 [Cifrar elementos XML con claves asimétricas](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
