---
title: GetXmlNamespace (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: bfccdcd9b5d35418b206dfa9fefffb5ddab69c66
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592168"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace (Operador) (Visual Basic)
Obtiene el objeto @no__t 0 que corresponde al prefijo de espacio de nombres XML especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>Elementos  
 `xmlNamespacePrefix`  
 Opcional. Cadena que identifica el prefijo del espacio de nombres XML. Si se proporciona, esta cadena debe ser un identificador XML válido. Para obtener más información, vea [nombres de elementos y atributos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md). Si no se especifica ningún prefijo, se devuelve el espacio de nombres predeterminado. Si no se especifica ningún espacio de nombres predeterminado, se devuelve el espacio de nombres vacío.  
  
## <a name="return-value"></a>Valor devuelto  
 Objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo del espacio de nombres XML.  
  
## <a name="remarks"></a>Comentarios  
 El operador `GetXmlNamespace` obtiene el objeto <xref:System.Xml.Linq.XNamespace> que corresponde al prefijo de espacio de nombres XML `xmlNamespacePrefix`.  
  
 Puede usar prefijos de espacio de nombres XML directamente en literales XML y propiedades de eje XML. Sin embargo, debe usar el operador `GetXmlNamespace` para convertir un prefijo de espacio de nombres en un objeto <xref:System.Xml.Linq.XNamespace> antes de poder usarlo en el código. Puede anexar un nombre de elemento no calificado a un objeto <xref:System.Xml.Linq.XNamespace> para obtener un objeto <xref:System.Xml.Linq.XName> completo, que requieren muchos métodos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se importa `ns` como prefijo de espacio de nombres XML. A continuación, usa el prefijo del espacio de nombres para crear un literal XML y acceder al primer nodo secundario que tiene el nombre completo `ns:phone`. A continuación, pasa ese nodo secundario a la subrutina `ShowName`, que construye un nombre completo mediante el operador `GetXmlNamespace`. A continuación, la subrutina `ShowName` pasa el nombre completo al método <xref:System.Xml.Linq.XNode.Ancestors%2A> para obtener el nodo primario `ns:contact`.  
  
 [!code-vb[VbXMLSamples#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/GetXmlNamespace.vb#38)]  
  
 Cuando se llama a `TestGetXmlNamespace.RunSample()`, se muestra un cuadro de mensaje que contiene el texto siguiente:  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>Vea también

- [Imports (instrucción), espacio de nombres XML](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Obtener acceso a XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
