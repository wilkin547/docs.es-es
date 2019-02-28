---
title: Filtrar Usar una clase genérica (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- type parameters [Visual Basic], defining
- data type arguments [Visual Basic], defining
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- generic parameters
- data type parameters
- generics [Visual Basic], about generics
- data types [Visual Basic], as parameters
- data types [Visual Basic], as arguments
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], creating generic types
- data type arguments
- parameters [Visual Basic], data type
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 242dd2a6-86c4-4ce7-83f2-f2661803f752
ms.openlocfilehash: e7d35a900ef4309963ff9de0ea77a12fd4577f12
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969679"
---
# <a name="how-to-use-a-generic-class-visual-basic"></a>Filtrar Usar una clase genérica (Visual Basic)
Las clases que toman *parámetros de tipo* se denominan *clases genéricas*. Si usa una clase genérica, puede generar una *clase construida* a partir de ella proporcionando un *argumento de tipo* para cada uno de estos parámetros. Después, puede declarar una variable del tipo de clase construida, crear una instancia de la clase construida y asignarla a esa variable.  
  
 Además de clases, también puede definir y usar estructuras genéricas, interfaces, procedimientos y delegados.  
  
 En el procedimiento siguiente se toma una clase genérica definida en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y se crea una instancia a partir de ella.  
  
### <a name="to-use-a-class-that-takes-a-type-parameter"></a>Para usar una clase que toma un parámetro de tipo  
  
1.  Al principio del archivo de origen, incluya una [instrucción Imports (tipo y Namespace. NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para importar el <xref:System.Collections.Generic?displayProperty=nameWithType> espacio de nombres. Esto le permite hacer referencia a la clase <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> sin tener que usar su nombre completo para diferenciarla de otras clases queue, como <xref:System.Collections.Queue?displayProperty=nameWithType>.  
  
2.  Cree el objeto de la manera normal, pero agregue `(Of type)` inmediatamente después del nombre de clase.  
  
     En el ejemplo siguiente se usa la misma clase (<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>) para crear dos objetos queue que contienen elementos de distintos tipos de datos. Agrega elementos al final de cada cola y, después, quita y muestra los elementos de la parte delantera de cada cola.  
  
     [!code-vb[VbVbalrDataTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Independencia del lenguaje y componentes independientes del lenguaje](../../../../standard/language-independence-and-language-independent-components.md)
- [Of](../../../../visual-basic/language-reference/statements/of-clause.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Cómo: Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Iteradores](../../../../visual-basic/programming-guide/concepts/iterators.md)
