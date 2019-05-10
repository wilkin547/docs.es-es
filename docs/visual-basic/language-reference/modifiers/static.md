---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f1031fe005a2fc264b50116b8ea3311dc7065dbc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647640"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Especifica uno o más variables locales declaradas deben seguir existiendo y conservar sus últimos valores tras la finalización del procedimiento en el que se declaran.  
  
## <a name="remarks"></a>Comentarios  
 Normalmente, una variable local en un procedimiento deja de existir en cuanto se detiene el procedimiento. Una variable estática sigue existiendo y conserva su valor más reciente. La próxima vez que el código llama al procedimiento, no se reinicializa la variable y todavía contiene el valor más reciente que asignó a él. Sigue existiendo durante la vigencia de la clase o módulo que está definido en una variable estática.  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Puede usar `Static` solo en las variables locales. Esto significa que el contexto de declaración de un `Static` variable debe ser un procedimiento o un bloque en un procedimiento y no puede ser el archivo de código fuente, espacio de nombres, clase, estructura o módulo.  
  
     No puede usar `Static` dentro de un procedimiento de estructura.  
  
- Los tipos de datos de `Static` las variables locales no se puede inferir. Para obtener más información, consulte [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
- **Modificadores combinados.** No puede especificar `Static` junto con `ReadOnly`, `Shadows`, o `Shared` en la misma declaración.  
  
## <a name="behavior"></a>Comportamiento  
 Cuando se declara una variable estática en un `Shared` procedimiento, solo una copia de la variable estática está disponible para toda la aplicación. Se llama a un `Shared` nombre de este procedimiento mediante el uso de la clase, no una variable que señala a una instancia de la clase.  
  
 Cuando se declara una variable estática en un procedimiento que no sea `Shared`, solo una copia de la variable está disponible para cada instancia de la clase. Llame a un procedimiento no compartido mediante una variable que señala a una instancia específica de la clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el uso de `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 El `Static` variable `totalSales` se inicializa en 0, solo una vez. Cada vez que escriba `updateSales`, `totalSales` sigue teniendo el valor más reciente que se ha calculado para él.  
  
 El `Static` modificador se puede usar en este contexto:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
