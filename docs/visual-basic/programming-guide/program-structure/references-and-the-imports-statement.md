---
title: Referencias y la instrucción Imports (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 9e31d22cd7502ffd405af23bd1fabe8685190221
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518131"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Referencias y la instrucción Imports (Visual Basic)
Se pueden objetos externos a disposición del proyecto eligiendo la **Agregar referencia** comando el **proyecto** menú. Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.  
  
## <a name="the-imports-statement"></a>La instrucción Imports  
 Los ensamblados incluyen uno o varios espacios de nombres. Cuando se agrega una referencia a un ensamblado, también puede agregar un `Imports` instrucción a un módulo que controla la visibilidad de espacios de nombres del ensamblado dentro del módulo. El `Imports` instrucción proporciona un ámbito de contexto que le permite usar sólo la parte del espacio de nombres necesarios para proporcionar una referencia única.  
  
 El `Imports` instrucción tiene la siguiente sintaxis:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname` hace referencia a un nombre corto que se puede usar dentro de código para hacer referencia a un espacio de nombres importado. `Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, mediante una definición dentro del proyecto o una anterior `Imports` instrucción.  
  
 Un módulo puede contener cualquier número de `Imports` instrucciones. Deben aparecer después de cualquier `Option` instrucciones, si está presente, pero antes de cualquier otro código.  
  
> [!NOTE]
>  No confunda las referencias de proyecto con el `Imports` instrucción o el `Declare` instrucción. Las referencias de proyecto disposición objetos externos, como los objetos de ensamblados, proyectos de Visual Basic. El `Imports` instrucción se usa para simplificar el acceso a las referencias de proyecto, pero no proporciona acceso a estos objetos. El `Declare` instrucción se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Uso de alias con la instrucción Imports  
 El `Imports` instrucción facilita acceso a los métodos de clases por lo que elimina la necesidad de escribir explícitamente los nombres completos de referencias. Los alias permiten asignar un nombre más descriptivo a sólo una parte de un espacio de nombres. Por ejemplo, el retorno de carro/avance la secuencia que produce un único fragmento de texto que se mostrará en varias líneas de línea es parte de la <xref:Microsoft.VisualBasic.ControlChars> módulo en el <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres. Para usar esta constante en un programa sin un alias, se tendría que escribir el código siguiente:  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports` instrucciones siempre deben ser las primeras líneas inmediatamente después de cualquier `Option` las instrucciones de un módulo. El fragmento de código siguiente muestra cómo importar y asignar un alias para el <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> módulo:  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Referencia futura a este espacio de nombres puede ser mucho más breves:  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Si un `Imports` instrucción no incluye un nombre de alias, se pueden usar elementos definidos en el espacio de nombres importado en el módulo sin calificación. Si se especifica el nombre de alias, debe usarse como calificador para los nombres dentro de ese espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Crear y utilizar ensamblados mediante la línea de comandos](https://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
