---
title: Características de los elementos declarados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
ms.openlocfilehash: 98f6a7738a462e9f36abdc0380cb1fe8d488fb9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821302"
---
# <a name="declared-element-characteristics-visual-basic"></a>Características de los elementos declarados (Visual Basic)
Un *característica* de un elemento declarado es un aspecto del elemento que afecta a cómo el código puede interactuar con él. Cada elemento declarado tiene una o varias de las siguientes características asociadas con él:  
  
-   *Tipo de datos* : los valores que puede contener el elemento y cómo almacena esos valores. Para más información, vea [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md).  
  
-   *Duración* : el período de tiempo de ejecución durante el cual el elemento está disponible para su uso. Para obtener más información, consulte [duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Ámbito* : el conjunto de todo el código que puede hacer referencia al elemento sin calificar su nombre. Para obtener más información, vea [Cómo: Controlar el ámbito de una Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Nivel de acceso* : el permiso de código hacer uso del elemento. Para obtener más información, vea [Cómo: Controlar la disponibilidad de una Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Características de los elementos  
 La siguiente tabla muestra los elementos declarados y las características que se aplican a cada uno de ellos.  
  
|Elemento|Tipo de datos|Período de duración|Ámbito <sup>1</sup>|Nivel de acceso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Sí|Sí|Sí|Sí|  
|Constante|Sí|No|Sí|Sí|  
|Enumeración|Sí|No|Sí|Sí|  
|Estructura|No|No|Sí|Sí|  
|Propiedad|Sí|Sí|Sí|Sí|  
|Método|No|Sí|Sí|Sí|  
|Procedimiento (`Sub` o `Function`)|No|Sí|Sí|Sí|  
|Parámetro de procedimiento|Sí|Sí|Sí|No|  
|Valor devuelto de función|Sí|Sí|Sí|No|  
|Operador|Sí|No|Sí|Sí|  
|Interfaz|No|No|Sí|Sí|  
|Clase|No|No|Sí|Sí|  
|evento|No|No|Sí|Sí|  
|delegado|No|No|Sí|Sí|  
  
 <sup>1</sup> ámbito a veces se conoce como *visibilidad*.  
  
## <a name="see-also"></a>Vea también

- [Elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
