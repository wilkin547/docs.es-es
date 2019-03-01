---
title: Literal de elemento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 71e6cf3e6169434ea0a28f8691cf82f6c8e8a030
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979939"
---
# <a name="xml-element-literal-visual-basic"></a>Literal de elemento XML (Visual Basic)

Un valor literal que representa un <xref:System.Xml.Linq.XElement> objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a>Elementos  
  
-   `<`  
  
     Obligatorio. Se abre la etiqueta inicial del elemento.  
  
-   `name`  
  
     Obligatorio. Nombre del elemento. El formato es uno de los siguientes:  
  
    -   Texto literal para el nombre del elemento, el formato `[ePrefix:]eName`, donde:  
  
        |Parte|Descripción|  
        |---|---|  
        |`ePrefix`|Opcional. Prefijo de espacio de nombres XML para el elemento. Debe ser un espacio de nombres XML global definido con un `Imports` instrucción en el archivo o en el nivel de proyecto, o un espacio de nombres XML que se define en este elemento o un elemento primario.|  
        |`eName`|Obligatorio. Nombre del elemento. El formato es uno de los siguientes:<br /><br /> -Texto literal. Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Incrustados de la expresión de formato `<%= eNameExp %>`. El tipo de `eNameExp` debe ser `String` o un tipo que es implícitamente convertible a <xref:System.Xml.Linq.XName>.|  
  
    -   La forma expresión incrustada `<%= nameExp %>`. El tipo de `nameExp` debe ser `String` o un tipo implícitamente convertible a <xref:System.Xml.Linq.XName>. No se permite una expresión incrustada en una etiqueta de cierre de un elemento.  
  
-   `attributeList`  
  
     Opcional. Lista de atributos declarados en el literal.  
  
     `attribute [ attribute ... ]`  
  
     Cada `attribute` tiene una de las siguientes sintaxis:  
  
    -   Asignación, el formato del atributo `[aPrefix:]aName=aValue`, donde:  
  
        |Parte|Descripción|  
        |---|---|  
        |`aPrefix`|Opcional. Prefijo de espacio de nombres XML para el atributo. Debe ser un espacio de nombres XML global definido con un `Imports` instrucción o un espacio de nombres XML que se define en este elemento o un elemento primario.|  
        |`aName`|Obligatorio. Nombre del atributo. El formato es uno de los siguientes:<br /><br /> -Texto literal. Consulte [nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).<br />-Incrustados de la expresión de formato `<%= aNameExp %>`. El tipo de `aNameExp` debe ser `String` o un tipo que es implícitamente convertible a <xref:System.Xml.Linq.XName>.|  
        |`aValue`|Opcional. Valor del atributo. El formato es uno de los siguientes:<br /><br /> -Texto literal, entrecomillada comillas.<br />-Incrustados de la expresión de formato `<%= aValueExp %>`. Se permite cualquier tipo.|  
  
    -   La forma expresión incrustada `<%= aExp %>`.  
  
-   `/>`  
  
     Opcional. Indica que el elemento es un elemento vacío sin contenido.  
  
-   `>`  
  
     Obligatorio. Finaliza la etiqueta del elemento inicial o vacío.  
  
-   `elementContents`  
  
     Opcional. Contenido del elemento.  
  
     `content [ content ... ]`  
  
     Cada `content` puede ser uno de los siguientes:  
  
    -   Texto literal. Todos los espacios en blanco `elementContents` pasa a ser significativa si no hay ningún texto literal.  
  
    -   La forma expresión incrustada `<%= contentExp %>`.  
  
    -   Literal de elemento XML.  
  
    -   Literal de comentario XML. Consulte [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).  
  
    -   Literal de instrucción de procesamiento de XML. Consulte [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).  
  
    -   XML CDATA literal. Consulte [Literal de CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).  
  
-   `</[name]>`  
  
     Opcional. Representa la etiqueta de cierre para el elemento. El elemento opcional `name` parámetro no se permite cuando es el resultado de una expresión incrustada.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto <xref:System.Xml.Linq.XElement>.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar la sintaxis de literales de elemento XML para crear <xref:System.Xml.Linq.XElement> objetos en el código.  
  
> [!NOTE]
>  Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea. Esta característica le permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.  
  
 Expresiones del formulario incrustadas `<%= exp %>` permiten agregar información dinámica a un literal de elemento XML. Para obtener más información, consulte [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 El compilador de Visual Basic convierte el literal de elemento XML en llamadas a la <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor y, si es necesario, el <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.  
  
## <a name="xml-namespaces"></a>Espacios de nombres XML  
 Los prefijos de espacio de nombres XML son útiles cuando tiene que crear literales XML con los elementos del mismo espacio de nombres muchas veces en el código. Puede usar globales prefijos de espacio de nombres XML, que se definen mediante el uso de la `Imports` instrucción o prefijos locales, que se definen mediante el uso de la `xmlns:xmlPrefix="xmlNamespace"` sintaxis de atributo. Para obtener más información, consulte [instrucción Imports (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
 Según las reglas de ámbito para los espacios de nombres XML, los prefijos locales tienen prioridad sobre los prefijos globales. Sin embargo, si un literal XML define un espacio de nombres XML, ese espacio de nombres no está disponible para las expresiones que aparecen en una expresión incrustada. La expresión insertada puede tener acceso a solo el espacio de nombres XML global.  
  
 El compilador de Visual Basic convierte cada espacio de nombres XML global que se usa un literal XML en una definición de un espacio de nombres local en el código generado. Los espacios de nombres XML globales que no se utilizan no aparecen en el código generado.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear un elemento XML simple que tiene dos elementos vacíos anidados.  
  
 [!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]  
  
 En el ejemplo se muestra el texto siguiente. Tenga en cuenta que el literal conserva la estructura de los elementos vacíos.  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo utilizar expresiones incrustadas para nombrar un elemento y crear atributos.  
  
 [!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]  
  
 Este código muestra el siguiente texto:  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara `ns` como un prefijo de espacio de nombres XML. A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y se muestra la forma final del elemento.  
  
 [!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]  
  
 Este código muestra el siguiente texto:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Tenga en cuenta que el compilador convirtió el prefijo del espacio de nombres XML global en una definición de prefijo del espacio de nombres XML. El \<ns:middle > elemento redefine el prefijo del espacio de nombres XML para el \<ns:inner1 > elemento. Sin embargo, el \<ns:inner2 > elemento utiliza el espacio de nombres definido por el `Imports` instrucción.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XElement>
- [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [Literal de CDATA XML](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Crear XML en Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports (instrucción), espacio de nombres XML](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
