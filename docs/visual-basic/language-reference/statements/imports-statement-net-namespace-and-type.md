---
title: 'Instrucción Imports: tipo y espacio de nombres .NET (Visual Basic)'
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
ms.openlocfilehash: a0b7a6a5fd16dc0daa620e6b490ddfdeb0e7c80e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912386"
---
# <a name="imports-statement-net-namespace-and-type"></a>Instrucción Imports (Tipo y espacio de nombres de .NET)
Permite hacer referencia a los nombres de tipo sin la calificación de espacio de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`aliasname`|Opcional. Un *alias de importación* o nombre con el que el código `namespace` puede hacer referencia en lugar de la cadena de calificación completa. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Necesario. Nombre completo del espacio de nombres que se va a importar. Puede ser una cadena de espacios de nombres anidados en cualquier nivel.|  
|`element`|Opcional. Nombre de un elemento de programación declarado en el espacio de nombres. Puede ser cualquier elemento contenedor.|  
  
## <a name="remarks"></a>Comentarios  
 La `Imports` instrucción permite hacer referencia directamente a los tipos contenidos en un espacio de nombres determinado.  
  
 Puede proporcionar un único nombre de espacio de nombres o una cadena de espacios de nombres anidados. Cada espacio de nombres anidado se separa del siguiente espacio de nombres de nivel superior`.`en un punto (), como se muestra en el ejemplo siguiente.  
  
 `Imports System.Collections.Generic`  
  
 Cada archivo de código fuente puede contener cualquier `Imports` número de instrucciones. Estos deben seguir cualquier declaración de opción, como la `Option Strict` instrucción, y deben preceder a cualquier declaración de elemento de programación, `Module` como instrucciones `Class` o.  
  
 Solo se puede `Imports` usar en el nivel de archivo. Esto significa que el contexto de la declaración para la importación debe ser un archivo de código fuente y no puede ser un espacio de nombres, una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque.  
  
 Tenga en cuenta `Imports` que la instrucción no hace que los elementos de otros proyectos y ensamblados estén disponibles para el proyecto. La importación no se ocupa del establecimiento de una referencia. Solo elimina la necesidad de calificar nombres que ya están disponibles para el proyecto. Para obtener más información, vea "importar elementos contenedores" en [referencias a elementos](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)declarados.  
  
> [!NOTE]
> Puede definir instrucciones implícitas `Imports` mediante la [Página referencias, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Para obtener más información, consulte [Cómo Agregar o quitar espacios de nombres importados (Visual Basic](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic)).  
  
## <a name="import-aliases"></a>Alias de importación  
 Un *alias de importación* define el alias de un espacio de nombres o de un tipo. Los alias de importación son útiles cuando es necesario usar elementos con el mismo nombre que se declaran en uno o varios espacios de nombres. Para obtener más información y un ejemplo, vea "calificar un nombre de elemento" en [referencias a elementos](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)declarados.  
  
 No debe declarar un miembro en el nivel de módulo con el mismo nombre `aliasname`que. Si lo hace, el compilador `aliasname` de Visual Basic solo utiliza para el miembro declarado y ya no lo reconoce como un alias de importación.  
  
 Aunque la sintaxis que se usa para declarar un alias de importación es similar a la que se usa para importar un prefijo de espacio de nombres XML, los resultados son diferentes. Un alias de importación se puede usar como una expresión en el código, mientras que un prefijo de espacio de nombres XML solo se puede usar en literales XML o propiedades de eje XML como prefijo para un nombre de elemento o atributo calificado.  
  
### <a name="element-names"></a>Nombres de elementos  
 Si proporciona `element`, debe representar un *elemento contenedor*, es decir, un elemento de programación que puede contener otros elementos. Los elementos de contenedor incluyen clases, estructuras, módulos, interfaces y enumeraciones.  
  
 El ámbito de los elementos que se ponen a `Imports` disposición de una instrucción depende de `element`si se especifica. Si solo `namespace`especifica, todos los miembros con el nombre único de ese espacio de nombres y los miembros de los elementos contenedores dentro de ese espacio de nombres están disponibles sin calificación. Si especifica `namespace` y `element`, solo estarán disponibles los miembros de ese elemento sin calificación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se devuelven todas las carpetas de C:\ directorio mediante la <xref:System.IO.DirectoryInfo> clase.  
  
 El código no tiene `Imports` ninguna instrucción en la parte superior del archivo. Por lo tanto `DirectoryInfo`, <xref:System.Text.StringBuilder>las referencias <xref:Microsoft.VisualBasic.ControlChars.CrLf> , y se califican totalmente con los espacios de nombres.  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `Imports` se incluyen instrucciones para los espacios de nombres a los que se hace referencia. Por lo tanto, no es necesario que los tipos estén completos con los espacios de nombres.  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `Imports` se incluyen instrucciones que crean alias para los espacios de nombres a los que se hace referencia. Los tipos se califican con los alias.  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `Imports` se incluyen instrucciones que crean alias para los tipos a los que se hace referencia. Los alias se usan para especificar los tipos.  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a>Vea también

- [Namespace (instrucción)](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports (instrucción), espacio de nombres XML](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
