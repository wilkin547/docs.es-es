---
title: XML Child Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: c6af9584931206fecde3154a91a60cfd38278ec0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873067"
---
# <a name="xml-child-axis-property-visual-basic"></a>Propiedades de eje secundario XML (Visual Basic)

Proporciona el acceso a los elementos secundarios de uno de los siguientes: un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`object`|Obligatorio. Un objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument>, una colección de objetos <xref:System.Xml.Linq.XElement> o una colección de objetos <xref:System.Xml.Linq.XDocument>.|  
|. <|Obligatorio. Denota el inicio de una propiedad de eje secundario.|  
|`child`|Obligatorio. Nombre de los nodos secundarios a los que se va a tener acceso, del formulario `[prefix:]name` .<br /><br /> -   `Prefix` Opta. Prefijo de espacio de nombres XML para el nodo secundario. Debe ser un espacio de nombres XML global definido con una instrucción `Imports`.<br />-   `Name` Desee. Nombre del nodo secundario local. Vea [nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).|  
|>|Obligatorio. Denota el final de una propiedad de eje secundario.|  
  
## <a name="return-value"></a>Valor devuelto  

 Una colección de objetos <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Comentarios  

 Puede usar una propiedad de eje secundario XML para tener acceso a los nodos secundarios por nombre desde un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, o desde una colección de objetos <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>. Utilice la propiedad XML `Value` para tener acceso al valor del primer nodo secundario de la colección devuelta. Para obtener más información, vea [propiedad valor XML](xml-value-property.md).  
  
 El compilador Visual Basic convierte las propiedades del eje secundario en llamadas al <xref:System.Xml.Linq.XContainer.Elements%2A> método.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  

 El nombre de una propiedad de eje secundario puede usar únicamente prefijos de espacios de nombres XML declarados globalmente con la instrucción `Imports`. No puede utilizar prefijos de espacio de nombres XML declarados localmente dentro de literales de elemento XML. Para obtener más información, vea [instrucción Imports (espacio de nombres XML)](../statements/imports-statement-xml-namespace.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo obtener acceso a los nodos secundarios llamados `phone` desde el objeto `contact`.  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 Este código muestra el siguiente texto:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo tener acceso a los nodos secundarios denominados `phone` desde la colección devuelta por la propiedad `contact` del eje secundario del objeto `contacts`.  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 Este código muestra el siguiente texto:  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 Este código muestra el siguiente texto:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XElement>
- [Propiedades de eje XML](index.md)
- [Literales XML](../xml-literals/index.md)
- [Crear XML en Visual Basic](../../programming-guide/language-features/xml/creating-xml.md)
- [Nombres de atributos y elementos XML declarados](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
