---
title: Procedimiento para descifrar elementos XML con claves asimétricas
ms.date: 07/14/2020
ms.technology: dotnet-standard
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
ms.openlocfilehash: 4a06628ddde0920133bfd74568786fbca6d5cf09
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556779"
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a>Procedimiento para descifrar elementos XML con claves asimétricas

Puede usar las clases en el espacio de nombres <xref:System.Security.Cryptography.Xml> para cifrar y descifrar un elemento dentro de un documento XML.  El cifrado XML es un método estándar para intercambiar o almacenar datos XML cifrados sin preocuparse de que los datos puedan leerse con facilidad.  Para obtener más información sobre el estándar de cifrado XML, vea la recomendación del World Wide Web Consortium (W3C) [sintaxis y procesamiento de firmas XML](https://www.w3.org/TR/xmldsig-core/).  

> [!NOTE]
> El código de este artículo se aplica a Windows.

El ejemplo de este procedimiento descifra un elemento XML cifrado mediante los métodos descritos en [Cómo: cifrar elementos XML con claves asimétricas](how-to-encrypt-xml-elements-with-asymmetric-keys.md).  Busca un elemento de `EncryptedData`> de <, descifra el elemento y, a continuación, reemplaza el elemento por el elemento XML de texto sin formato original.  
  
En este ejemplo se descifra un elemento XML mediante dos claves.  Recupera una clave privada RSA generada previamente a partir de un contenedor de claves y, a continuación, usa la clave RSA para descifrar una clave de sesión almacenada en el `EncryptedKey` elemento <> del `EncryptedData` elemento> <.  Luego, el ejemplo usa la clave de sesión para descifrar el elemento XML.  
  
Este ejemplo resulta adecuado en aquellas situaciones en las que varias aplicaciones tienen que compartir datos cifrados o en las que una aplicación tiene que guardar datos cifrados entre los intervalos en los que se ejecuta.  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a>Para descifrar un elemento XML con una clave asimétrica  
  
1. Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2. Recupere una clave asimétrica previamente generada desde el contenedor mediante el objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  La clave se recupera automáticamente del contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3. Cree un objeto <xref:System.Security.Cryptography.Xml.EncryptedXml> nuevo para descifrar el documento.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4. Agregue una asignación de clave/nombre para asociar la clave RSA al elemento del documento que se debe descifrar.  Debe usar el mismo nombre para la clave que usó al cifrar el documento.  Tenga en cuenta que este nombre es independiente del que haya usado para identificar la clave en el contenedor de claves especificado en el paso 1.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5. Llame al <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> método para descifrar el elemento de> de <`EncryptedData` .  Este método usa la clave RSA para descifrar la clave de sesión y la usa automáticamente para descifrar el elemento XML.  También reemplaza automáticamente el elemento <`EncryptedData`> por el texto sin formato original.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6. Guarde el documento XML.  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a>Ejemplo

En este ejemplo se supone que un archivo llamado `test.xml` se encuentra en el mismo directorio que el programa compilado.  También se supone que `test.xml` contiene un elemento XML cifrado mediante las técnicas descritas en [Cómo: cifrar elementos XML con claves asimétricas](how-to-encrypt-xml-elements-with-asymmetric-keys.md).  
  
[!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
[!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- En un proyecto que tiene como destino .NET Framework, incluya una referencia a `System.Security.dll` .

- En un proyecto que tenga como destino .NET Core o .NET 5, instale el paquete NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).
  
- Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-security"></a>Seguridad de .NET  

No almacene nunca una clave criptográfica simétrica en texto sin formato ni transfiera una clave simétrica entre equipos en texto sin formato.  Tampoco debe almacenar ni transferir nunca la clave privada de un par de claves asimétricas en texto sin formato.  Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](generating-keys-for-encryption-and-decryption.md).  
  
 No inserte nunca una clave directamente en el código fuente.  Las claves incrustadas se pueden leer fácilmente desde un ensamblado mediante [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como el Bloc de notas.  
  
 Cuando termine de usar una clave criptográfica, bórrela de la memoria estableciendo cada byte en cero o llamando al método <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> de la clase criptográfica administrada.  A veces, las claves criptográficas se pueden leer desde la memoria con un depurador o desde un disco duro si la ubicación de memoria se pagina en el disco.  
  
## <a name="see-also"></a>Consulte también

- [Modelo de criptografía](cryptography-model.md)
- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [Procedimiento para cifrar elementos XML con claves asimétricas](how-to-encrypt-xml-elements-with-asymmetric-keys.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
