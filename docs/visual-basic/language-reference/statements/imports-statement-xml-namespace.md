---
title: Imports (instrucción) - Namespace XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 8cce1cc918b150fdf30449f127b1e2f0a73e6f6c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973280"
---
# <a name="imports-statement-xml-namespace"></a>Imports (Instrucción, Espacio de nombres XML)
Importa los prefijos de espacio de nombres XML para su uso en literales XML y propiedades de eje XML.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Elementos  
 `xmlNamespacePrefix`  
 Opcional. La cadena de forma que el código XML a los elementos y atributos pueden hacer referencia a `xmlNamespaceName`. Si no hay ningún `xmlNamespacePrefix` es proporcionado, el espacio de nombres XML importado es el espacio de nombres XML predeterminado. Debe ser un identificador XML válido. Para obtener más información, consulte [atributos y los nombres de los elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Obligatorio. Cadena que identifica el espacio de nombres XML que se va a importar.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Imports` instrucción para definir los espacios de nombres XML globales que puede usar con literales XML y propiedades de eje XML o como parámetros pasados a la `GetXmlNamespace` operador. (Para obtener información sobre el uso de la `Imports` instrucción para importar un alias que se puede utilizar donde se usan los nombres de tipo en el código, consulte [instrucción Imports (tipo y Namespace. NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) La sintaxis para declarar un espacio de nombres XML mediante el uso de la `Imports` instrucción es idéntica a la sintaxis utilizada en XML. Por lo tanto, puede copiar una declaración de espacio de nombres de un archivo XML y usarlo en un `Imports` instrucción.  
  
 Los prefijos de espacio de nombres XML son útiles cuando desea crear repetidamente elementos XML que están en el mismo espacio de nombres. El prefijo del espacio de nombres XML declarados con el `Imports` instrucción es global en el sentido de que está disponible para todo el código en el archivo. Puede usarlo al crear literales de elemento XML y al acceder a propiedades de eje XML. Para obtener más información, consulte [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/index.md).  
  
 Si se define un espacio de nombres XML global sin un prefijo de espacio de nombres (por ejemplo, `Imports <xmlns="http://SomeNameSpace>"`), ese espacio de nombres se considera el espacio de nombres XML predeterminado. Espacio de nombres XML predeterminado se usa para los literales de elemento XML o propiedades de eje de atributo XML que no se especifican explícitamente un espacio de nombres. El espacio de nombres predeterminado también se usa si el espacio de nombres especificado es el espacio de nombres vacío (es decir, `xmlns=""`). Espacio de nombres XML predeterminado no se aplica a los atributos XML en literales XML o propiedades del eje de atributo XML que no tienen un espacio de nombres.  
  
 Espacios de nombres XML que se definen en un literal XML, que se denominan *espacios de nombres XML local*, tienen prioridad sobre los espacios de nombres XML que se definen mediante la `Imports` instrucción como globales. Espacios de nombres XML que se definen mediante la `Imports` instrucción tienen prioridad sobre los espacios de nombres XML importado para un proyecto de Visual Basic. Si un literal XML define un espacio de nombres XML, ese espacio de nombres local no es aplicable a las expresiones incrustadas.  
  
 Espacios de nombres XML globales siguen las mismas reglas de ámbito y definición que los espacios de nombres de .NET Framework. Como resultado, puede incluir un `Imports` instrucción para definir un espacio de nombres XML global en cualquier lugar puede importar un espacio de nombres de .NET Framework. Esto incluye los archivos de código y espacios de nombres importados de nivel de proyecto. Para obtener información acerca de espacios de nombres importados de nivel de proyecto, vea [página referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones. Éstas deben seguir las declaraciones de opción, como el `Option Strict` instrucción y se deben preceder a declaraciones de elemento de programación, como `Module` o `Class` instrucciones.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa el espacio de nombres XML predeterminado y un espacio de nombres XML identificado por el prefijo `ns`. A continuación, crea los literales XML que utilizan ambos espacios de nombres.  
  
 [!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]  
  
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
 El ejemplo siguiente importa el prefijo del espacio de nombres XML `ns`. A continuación, crea un literal XML que usa el prefijo de espacio de nombres y muestra la forma final del elemento.  
  
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
  
 Tenga en cuenta que el compilador convirtió el prefijo del espacio de nombres XML de un prefijo global a una definición de prefijo local.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente importa el prefijo del espacio de nombres XML `ns`. A continuación, se usa el prefijo del espacio de nombres para crear un literal XML y obtener acceso al primer nodo secundario con el nombre completo `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 Este código muestra el siguiente texto:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Vea también
- [Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Propiedades del eje XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Nombres de atributos y elementos XML declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [GetXmlNamespace (operador)](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
