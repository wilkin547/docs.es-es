---
description: 'Más información sobre: referencias y la instrucción Imports (Visual Basic)'
title: Instrucción Imports y referencias
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 3ca685d33f69224a6eea324d7357be4b5203eb45
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468244"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Referencias y la instrucción Imports (Visual Basic)

Puede hacer que los objetos externos estén disponibles para el proyecto eligiendo el comando **Agregar referencia** en el menú **proyecto** . Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.  
  
## <a name="the-imports-statement"></a>La instrucción Imports  

 Los ensamblados incluyen uno o varios espacios de nombres. Al agregar una referencia a un ensamblado, también puede Agregar una `Imports` instrucción a un módulo que controla la visibilidad de los espacios de nombres de ese ensamblado en el módulo. La `Imports` instrucción proporciona un contexto de ámbito que le permite usar solo la parte del espacio de nombres necesaria para proporcionar una referencia única.  
  
 La `Imports` instrucción tiene la siguiente sintaxis:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` hace referencia a un nombre corto que puede usar en el código para hacer referencia a un espacio de nombres importado. `Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, a través de una definición dentro del proyecto o a través de una `Imports` instrucción anterior.  
  
 Un módulo puede contener cualquier número de `Imports` instrucciones. Deben aparecer después de cualquier `Option` instrucción, si está presente, pero antes de cualquier otro código.  
  
> [!NOTE]
> No confunda las referencias de proyecto con la `Imports` instrucción o la `Declare` instrucción. Las referencias de proyecto hacen que los objetos externos, como los objetos de los ensamblados, estén disponibles para proyectos de Visual Basic. La `Imports` instrucción se usa para simplificar el acceso a las referencias del proyecto, pero no proporciona acceso a estos objetos. La `Declare` instrucción se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (dll).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Usar alias con la instrucción Imports  

 La `Imports` instrucción facilita el acceso a los métodos de las clases, ya que elimina la necesidad de escribir explícitamente los nombres completos de las referencias. Los alias permiten asignar un nombre más descriptivo a solo una parte de un espacio de nombres. Por ejemplo, la secuencia de retorno de carro/avance de línea que hace que se muestre un único fragmento de texto en varias líneas es parte del <xref:Microsoft.VisualBasic.ControlChars> módulo en el <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres. Para usar esta constante en un programa sin un alias, debe escribir el código siguiente:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` las instrucciones siempre deben ser las primeras líneas inmediatamente después `Option` de cualquier instrucción de un módulo. En el siguiente fragmento de código se muestra cómo importar y asignar un alias al <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> módulo:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Las referencias futuras a este espacio de nombres pueden ser mucho más cortas:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Si una `Imports` instrucción no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado se pueden usar en el módulo sin calificación. Si se especifica el nombre de alias, se debe usar como calificador para los nombres contenidos dentro de ese espacio de nombres.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Espacios de nombres en Visual Basic](namespaces.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
