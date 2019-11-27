---
title: Referencias y la instrucción Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 31b4fe001f2b8a62ac30488053c57cd186020421
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347272"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Referencias y la instrucción Imports (Visual Basic)
Puede hacer que los objetos externos estén disponibles para el proyecto eligiendo el comando **Agregar referencia** en el menú **proyecto** . Las referencias en Visual Basic pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.  
  
## <a name="the-imports-statement"></a>La instrucción Imports  
 Los ensamblados incluyen uno o varios espacios de nombres. Al agregar una referencia a un ensamblado, también puede Agregar una instrucción `Imports` a un módulo que controla la visibilidad de los espacios de nombres de ese ensamblado en el módulo. La instrucción `Imports` proporciona un contexto de ámbito que le permite usar solo la parte del espacio de nombres necesaria para proporcionar una referencia única.  
  
 La instrucción `Imports` tiene la siguiente sintaxis:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` hace referencia a un nombre corto que puede usar en el código para hacer referencia a un espacio de nombres importado. `Namespace` es un espacio de nombres disponible a través de una referencia de proyecto, a través de una definición dentro del proyecto o a través de una instrucción de `Imports` anterior.  
  
 Un módulo puede contener cualquier número de instrucciones `Imports`. Deben aparecer después de cualquier instrucción `Option`, si está presente, pero antes de cualquier otro código.  
  
> [!NOTE]
> No confunda las referencias de proyecto con la instrucción `Imports` o la instrucción `Declare`. Las referencias de proyecto hacen que los objetos externos, como los objetos de los ensamblados, estén disponibles para proyectos de Visual Basic. La instrucción `Imports` se usa para simplificar el acceso a las referencias del proyecto, pero no proporciona acceso a estos objetos. La instrucción `Declare` se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Usar alias con la instrucción Imports  
 La instrucción `Imports` facilita el acceso a los métodos de las clases, ya que elimina la necesidad de escribir explícitamente los nombres completos de las referencias. Los alias permiten asignar un nombre más descriptivo a solo una parte de un espacio de nombres. Por ejemplo, la secuencia de retorno de carro/avance de línea que hace que se muestre un único fragmento de texto en varias líneas forma parte del módulo de <xref:Microsoft.VisualBasic.ControlChars> en el espacio de nombres <xref:Microsoft.VisualBasic?displayProperty=nameWithType>. Para usar esta constante en un programa sin un alias, debe escribir el código siguiente:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` instrucciones siempre deben ser las primeras líneas inmediatamente después de cualquier instrucción `Option` de un módulo. En el siguiente fragmento de código se muestra cómo importar y asignar un alias al módulo <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Las referencias futuras a este espacio de nombres pueden ser mucho más cortas:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Si una instrucción `Imports` no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado se pueden usar en el módulo sin calificación. Si se especifica el nombre de alias, se debe usar como calificador para los nombres contenidos dentro de ese espacio de nombres.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Espacios de nombres en Visual Basic](namespaces.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
