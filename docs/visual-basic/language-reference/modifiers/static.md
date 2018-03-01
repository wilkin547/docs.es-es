---
title: Static (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e08f46076281e766a5bc0b99cd61fee9cd41ece5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Especifica que una o varias variables locales declaradas deben seguir existiendo y conservar sus últimos valores tras la finalización del procedimiento en el que se declaran.  
  
## <a name="remarks"></a>Comentarios  
 Normalmente, una variable local en un procedimiento deja de existir cuando se detiene el procedimiento. Una variable estática sigue existiendo y conserva su valor más reciente. La próxima vez que el código llama al procedimiento, no se reinicializa la variable y se mantiene el último valor asignado a él. Una variable estática sigue existiendo durante la vigencia de la clase o módulo que se define en.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Puede usar `Static` solo en las variables locales. Esto significa que el contexto de la declaración de un `Static` variable debe ser un procedimiento o un bloque en un procedimiento y no puede ser un archivo de código fuente, espacio de nombres, clase, estructura o módulo.  
  
     No se puede utilizar `Static` dentro de un procedimiento de estructura.  
  
-   Los tipos de datos de `Static` no se pueden inferir variables locales. Para obtener más información, consulte [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Modificadores combinados.** No se puede especificar `Static` junto con `ReadOnly`, `Shadows`, o `Shared` en la misma declaración.  
  
## <a name="behavior"></a>Comportamiento  
 Cuando se declara una variable estática en un `Shared` procedimiento, solo una copia de la variable estática está disponible para toda la aplicación. Se llama a un `Shared` nombre de este procedimiento mediante la clase, no una variable que apunta a una instancia de la clase.  
  
 Cuando se declara una variable estática en un procedimiento que no es `Shared`, sólo una copia de la variable está disponible para cada instancia de la clase. Se llama a un procedimiento no compartido mediante una variable que apunta a una instancia específica de la clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el uso de `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 El `Static` variable `totalSales` se inicializa en 0 solo una vez. Cada vez que escriba `updateSales`, `totalSales` aún tiene el valor más reciente que se ha calculado para él.  
  
 El `Static` modificador se puede usar en este contexto:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Declaración de variables](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
