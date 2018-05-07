---
title: Instrucción Imports (Tipo y espacio de nombres de .NET)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: ef569b0ed6428d24d019e00c500e4d4b91c83d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imports-statement-net-namespace-and-type"></a>Instrucción Imports (Tipo y espacio de nombres de .NET)
Permite nombres que hace referencia sin calificación de espacio de nombres de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`aliasname`|Opcional. Un *alias de importación* o el nombre por el que el código puede hacer referencia a `namespace` en lugar de la cadena de calificación completa. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Requerido. El nombre completo del espacio de nombres que se va a importar. Puede ser una cadena de espacios de nombres anidada a cualquier nivel.|  
|`element`|Opcional. El nombre de un elemento de programación declarado en el espacio de nombres. Puede ser cualquier elemento contenedor.|  
  
## <a name="remarks"></a>Comentarios  
 El `Imports` instrucción permite los tipos que se encuentran en un espacio de nombres que hace referencia directamente.  
  
 Puede proporcionar un nombre de espacio de nombres único o una cadena de espacios de nombres anidados. Cada espacio de nombres anidado se separa del siguiente espacio de nombres de nivel superior con un punto (`.`), como se muestra en el ejemplo siguiente.  
  
 `Imports System.Collections.Generic`  
  
 Cada archivo de código fuente puede contener cualquier número de `Imports` instrucciones. Éstas deben seguir las declaraciones de opción existentes, como el `Option Strict` instrucción y se debe preceder a cualquier declaración de elemento de programación como `Module` o `Class` las instrucciones.  
  
 Puede usar `Imports` sólo en el nivel de archivo. Esto significa que el contexto de la declaración para la importación debe ser un archivo de origen y no puede ser un espacio de nombres, clase, estructura, módulo, interfaz, procedimiento o bloque.  
  
 Tenga en cuenta que el `Imports` instrucción no hace que estén disponibles para el proyecto de elementos de otros proyectos y ensamblados. La importación no ocupar el lugar de establecer una referencia. Sólo quita la necesidad de calificar nombres que ya están disponibles para el proyecto. Para obtener más información, vea "Importar elementos contenedores" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Puede definir implícita `Imports` instrucciones mediante el uso de la [página referencias, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Para obtener más información, consulte [Cómo: agregar o quitar espacios de nombres importados (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
## <a name="import-aliases"></a>Alias de importación  
 Un *alias de importación* define el alias para un espacio de nombres o tipo. Alias de importación son útiles cuando necesite utilizar los elementos con el mismo nombre que se declaran en uno o varios espacios de nombres. Para obtener más información y un ejemplo, vea "Calificar un nombre de elemento" en [referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 No se deben declarar un miembro en el nivel de módulo con el mismo nombre que `aliasname`. Si lo hace, el compilador de Visual Basic utiliza `aliasname` solo para el miembro declarado y ya no se reconoce como un alias de importación.  
  
 Aunque la sintaxis utilizada para declarar un alias de importación que se utiliza para importar un prefijo de espacio de nombres XML, los resultados son diferentes. Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML se puede utilizar únicamente en literales XML o propiedades de eje XML como el prefijo para un elemento completo o el nombre del atributo.  
  
### <a name="element-names"></a>Nombres de elementos  
 Si proporciona `element`, debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos. Elementos contenedores incluyen clases, estructuras, módulos, interfaces y enumeraciones.  
  
 El ámbito de los elementos facilitados por un `Imports` instrucción depende de si se especifica `element`. Si solo especifica `namespace`, todo de forma exclusiva con el nombre de los miembros de ese espacio de nombres y los miembros de elementos contenedores dentro de ese espacio de nombres, están disponibles sin calificación. Si se especifican ambas `namespace` y `element`, solo los miembros de ese elemento están disponibles sin calificación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente devuelve todas las carpetas en el directorio C:\ utilizando la <xref:System.IO.DirectoryInfo> clase.  
  
 El código no tiene ningún `Imports` las instrucciones en la parte superior del archivo. Por lo tanto, la `DirectoryInfo`, <xref:System.Text.StringBuilder>, y <xref:Microsoft.VisualBasic.ControlChars.CrLf> referencias son todos los nombres completos con los espacios de nombres.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se incluye `Imports` instrucciones para los espacios de nombres que se hace referencia. Por lo tanto, los tipos no tiene que ser un nombre completo con los espacios de nombres.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se incluye `Imports` instrucciones que crean los alias para los espacios de nombres que se hace referencia. Los tipos se califican con el alias.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se incluye `Imports` instrucciones que crean los alias para los tipos que se hace referencia. Alias se usan para especificar los tipos.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Imports (instrucción), espacio de nombres XML](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
