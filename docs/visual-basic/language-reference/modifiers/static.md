---
title: estática
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 3b323d5fb1c4f1357b9f476213793c69d29b7208
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402699"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Especifica que una o varias variables locales declaradas deben seguir existiendo y conservar sus valores más recientes después de la finalización del procedimiento en el que se declaran.  
  
## <a name="remarks"></a>Observaciones  
 Normalmente, una variable local de un procedimiento deja de existir en cuanto se detiene el procedimiento. Una variable estática sigue existiendo y conserva su valor más reciente. La próxima vez que el código llame al procedimiento, no se reinicializará la variable y se conservará el valor más reciente que le haya asignado. Una variable estática sigue existiendo mientras dure la clase o el módulo en el que se define.  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Solo se puede usar `Static` en variables locales. Esto significa que el contexto de la declaración de una `Static` variable debe ser un procedimiento o un bloque de un procedimiento, y no puede ser un archivo de código fuente, un espacio de nombres, una clase, una estructura o un módulo.  
  
     No se puede usar `Static` dentro de un procedimiento de estructura.  
  
- No se pueden inferir los tipos de datos de `Static` las variables locales. Para obtener más información, vea [inferencia de tipo local](../../programming-guide/language-features/variables/local-type-inference.md).  
  
- **Modificadores combinados.** No se puede especificar `Static` junto con `ReadOnly` , `Shadows` o `Shared` en la misma declaración.  
  
## <a name="behavior"></a>Comportamiento  
 Cuando se declara una variable estática en un `Shared` procedimiento, solo hay una copia de la variable estática disponible para toda la aplicación. Se llama a un `Shared` procedimiento mediante el nombre de clase, no una variable que apunta a una instancia de la clase.  
  
 Cuando se declara una variable estática en un procedimiento que no es `Shared` , solo está disponible una copia de la variable para cada instancia de la clase. Se llama a un procedimiento no compartido mediante una variable que apunta a una instancia específica de la clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra el uso de `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 La `Static` variable `totalSales` se inicializa en 0 solo una vez. Cada vez que escriba `updateSales` , `totalSales` seguirá teniendo el valor más reciente que calculó para él.  
  
 El `Static` modificador se puede usar en este contexto:  
  
 [Instrucción Dim](../statements/dim-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Shadows](shadows.md)
- [Compartido](shared.md)
- [Período de duración en Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Declaración de variable](../../programming-guide/language-features/variables/variable-declaration.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
