---
title: "Imports (Instrucción, Espacio de nombres XML)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0fe6d37c58ead94f2c03736318209abb67cd6dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imports-statement-xml-namespace"></a>Imports (Instrucción, Espacio de nombres XML)
Importa los prefijos de espacio de nombres XML para su uso en literales XML y propiedades de eje XML.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Elementos  
 `xmlNamespacePrefix`  
 Opcional. La cadena de forma que el código XML a elementos y atributos pueden hacer referencia a `xmlNamespaceName`. Si no hay ningún `xmlNamespacePrefix` es proporcionado, el espacio de nombres XML importado es el espacio de nombres XML de forma predeterminada. Debe ser un identificador XML válido. Para obtener más información, consulte [nombres de declarar elementos y atributos XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Obligatorio. Cadena que identifica el espacio de nombres XML que se va a importar.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Imports` instrucción para definir los espacios de nombres XML globales que puede usar con literales XML y propiedades de eje XML o como parámetros pasados a la `GetXmlNamespace` operador. (Para obtener información sobre el uso de la `Imports` statement para importar un alias que se puede utilizar donde se utilizan los nombres de tipo en el código, vea [Imports (instrucción Namespace de .NET y tipo)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) La sintaxis para declarar un espacio de nombres XML mediante el uso de la `Imports` instrucción es idéntica a la sintaxis utilizada en XML. Por lo tanto, puede copiar una declaración de espacio de nombres de un archivo XML y usarlo en un `Imports` instrucción.  
  
 Prefijos de espacio de nombres XML son útiles cuando desea crear repetidamente elementos XML que están en el mismo espacio de nombres. El prefijo de espacio de nombres XML declarados con la `Imports` instrucción es global en el sentido de que está disponible para todo el código en el archivo. Se puede utilizar cuando cree literales de elemento XML y al acceder a propiedades de eje XML. Para obtener más información, consulte [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).  
  
 Si se define un espacio de nombres XML global sin un prefijo de espacio de nombres (por ejemplo, `Imports <xmlns="http://SomeNameSpace>"`), ese espacio de nombres se considera el espacio de nombres XML predeterminado. Espacio de nombres XML predeterminado se utiliza para los literales de elemento XML o propiedades de eje de atributo XML que no especifiquen explícitamente un espacio de nombres. El espacio de nombres predeterminado también se utiliza si el espacio de nombres especificado es el espacio de nombres vacío (es decir, `xmlns=""`). Espacio de nombres XML predeterminado no se aplica a los atributos XML en literales XML o propiedades de eje de atributo XML que no tiene un espacio de nombres.  
  
 Espacios de nombres XML que se definen en un literal XML, que se denominan *local espacios de nombres XML*, tienen prioridad sobre los espacios de nombres XML que se definen mediante el `Imports` instrucción como global. Espacios de nombres XML que se definen mediante el `Imports` instrucción tienen prioridad sobre los espacios de nombres XML importados para un proyecto de Visual Basic. Si un literal XML define un espacio de nombres XML, ese espacio de nombres local no se aplica a las expresiones incrustadas.  
  
 Espacios de nombres XML globales siguen las mismas reglas de ámbito y definición como espacios de nombres de .NET Framework. Como resultado, puede incluir un `Imports` instrucción para definir un espacio de nombres XML global donde pueda importar un espacio de nombres de .NET Framework. Esto incluye archivos de código y espacios de nombres importados de nivel de proyecto. Para obtener información acerca de espacios de nombres importados de nivel de proyecto, vea [página referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones. Éstas deben seguir las declaraciones de opción, como el `Option Strict` instrucción y se deben preceder a declaraciones de elemento de programación, como `Module` o `Class` las instrucciones.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa el espacio de nombres XML predeterminado y un espacio de nombres XML identificado por el prefijo `ns`. A continuación, crea literales XML que utilizan ambos espacios de nombres.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 Este código muestra el siguiente texto:  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa el prefijo de espacio de nombres XML `ns`. A continuación, crea un literal XML que utiliza el prefijo de espacio de nombres y se muestra la forma final del elemento.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Este código muestra el siguiente texto:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Tenga en cuenta que el compilador convirtió el prefijo del espacio de nombres XML de un prefijo global a una definición de prefijo local.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa el prefijo de espacio de nombres XML `ns`. A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Este código muestra el siguiente texto:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Vea también  
 [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [GetXmlNamespace (operador)](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
