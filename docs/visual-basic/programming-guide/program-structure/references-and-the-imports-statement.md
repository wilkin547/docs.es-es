---
title: "Referencias y la instrucción Imports (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 283a27e7703b31a9aeed8f7e4104e89b7ff78525
ms.lasthandoff: 03/13/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a>Referencias y la instrucción Imports (Visual Basic)
Puedan disponer objetos externos a su proyecto eligiendo la **Agregar referencia** comando el **proyecto** menú. Referencias en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] pueden apuntar a ensamblados, que son similares a las bibliotecas de tipos, pero contienen más información.  
  
## <a name="the-imports-statement"></a>La instrucción Imports  
 Los ensamblados incluyen uno o más espacios de nombres. Cuando se agrega una referencia a un ensamblado, también puede agregar un `Imports` instrucción a un módulo que controla la visibilidad de los espacios de nombres del ensamblado dentro del módulo. El `Imports` instrucción proporciona un contexto de ámbito que permite utilizar sólo la parte del espacio de nombres necesaria para suministrar una referencia única.  
  
 El `Imports` instrucción tiene la siguiente sintaxis:  
  
 `Imports` [`|``Aliasname` =] `Namespace`  
  
 `Aliasname`hace referencia a un nombre corto que se puede utilizar dentro de código para hacer referencia a un espacio de nombres importado. `Namespace`es un espacio de nombres disponible a través de una referencia de proyecto a través de una definición dentro del proyecto o una anterior `Imports` instrucción.  
  
 Un módulo puede contener cualquier número de `Imports` instrucciones. Deben aparecer después de cualquier `Option` instrucciones, si está presente, pero antes de cualquier otro código.  
  
> [!NOTE]
>  No confunda las referencias de proyecto con el `Imports` instrucción o `Declare` instrucción. Referencias de proyecto disponer de objetos externos, como los objetos de ensamblados, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proyectos. El `Imports` instrucción se usa para simplificar el acceso a las referencias del proyecto, pero no proporciona acceso a estos objetos. El `Declare` instrucción se utiliza para declarar una referencia a un procedimiento externo en una biblioteca de vínculos dinámicos (DLL).  
  
## <a name="using-aliases-with-the-imports-statement"></a>Uso de alias con la instrucción Imports  
 El `Imports` instrucción hace más fácil acceso a los métodos de clases, lo que elimina la necesidad de escribir explícitamente los nombres completos de las referencias. Los alias permiten asignar un nombre más descriptivo a sólo una parte de un espacio de nombres. Por ejemplo, el retorno de carro/avance de secuencia que hace que un único fragmento de texto se muestre en varias líneas de línea es parte de la <xref:Microsoft.VisualBasic.ControlChars>módulo en el <xref:Microsoft.VisualBasic?displayProperty=fullName>espacio de nombres.</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars> Para utilizar esta constante en un programa sin un alias, se tendría que escribir el código siguiente:  
  
 [!code-vb[VbVbalrApplication&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 `Imports`instrucciones siempre deben ser las primeras líneas inmediatamente después de cualquier `Option` instrucciones de un módulo. El siguiente fragmento de código muestra cómo importar y asignar un alias a la <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>módulo:</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>  
  
 [!code-vb[VbVbalrApplication Nº&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 Referencia futura a este espacio de nombres puede ser mucho más breves:  
  
 [!code-vb[VbVbalrApplication&#5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 Si un `Imports` instrucción no incluye un nombre de alias, los elementos definidos en el espacio de nombres importado pueden utilizarse en el módulo sin calificación. Si se especifica el nombre de alias, debe utilizarse como calificador de nombres contenidos en ese espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars>   
 <xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic>   
 [Cómo: Agregar o quitar referencias utilizando el cuadro de diálogo Agregar referencia](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Cómo: crear y utilizar ensamblados desde la línea de comandos](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)   
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
