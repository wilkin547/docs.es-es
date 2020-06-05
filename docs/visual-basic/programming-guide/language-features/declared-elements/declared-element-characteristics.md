---
title: Características de los elementos declarados
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
ms.openlocfilehash: 9d1e327c25689bed1405ea9a627da6232abb707b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392953"
---
# <a name="declared-element-characteristics-visual-basic"></a>Características de los elementos declarados (Visual Basic)
Una *característica* de un elemento declarado es un aspecto de ese elemento que afecta al modo en que el código puede interactuar con él. Cada elemento declarado tiene una o varias de las siguientes características asociadas:  
  
- *Tipo de datos* : los valores que el elemento puede contener y cómo almacena esos valores. Para más información, vea [Tipos de datos](../../../language-reference/data-types/index.md).  
  
- *Duración* : el período de tiempo de ejecución durante el cual el elemento está disponible para su uso. Para obtener más información, vea [duración en Visual Basic](lifetime.md).  
  
- *Ámbito* : el conjunto de todo el código que puede hacer referencia al elemento sin calificar su nombre. Para obtener más información, vea [Cómo: controlar el ámbito de una variable](how-to-control-the-scope-of-a-variable.md).  
  
- *Nivel de acceso* : permiso para que el código haga uso del elemento. Para obtener más información, vea [Cómo: controlar la disponibilidad de una variable](how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Características de los elementos  
 En la tabla siguiente se muestran los elementos declarados y las características que se aplican a cada uno de ellos.  
  
|Elemento|Tipo de datos|Vigencia|Ámbito <sup>1</sup>|Nivel de acceso|  
|-------------|---------------|--------------|------------------------|------------------|  
|Variable|Sí|Sí|Sí|Sí|  
|Constante|Sí|No|Sí|Sí|  
|Enumeración|Sí|No|Sí|Sí|  
|Estructura|No|No|Sí|Sí|  
|Propiedad|Sí|Sí|Sí|Sí|  
|Método|No|Sí|Sí|Sí|  
|Procedimiento ( `Sub` o `Function` )|No|Sí|Sí|Sí|  
|Parámetro de procedimiento|Sí|Sí|Sí|No|  
|Devolución de función|Sí|Sí|Sí|No|  
|Operador|Sí|No|Sí|Sí|  
|Interfaz|No|No|Sí|Sí|  
|Class|No|No|Sí|Sí|  
|Evento|No|No|Sí|Sí|  
|Delegado|No|No|Sí|Sí|  
  
 <sup>1</sup> el ámbito se denomina a veces *visibilidad*.  
  
## <a name="see-also"></a>Consulte también

- [Elementos declarados](index.md)
- [Declared Element Names](declared-element-names.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Período de duración en Visual Basic](lifetime.md)
- [Ámbito en Visual Basic](scope.md)
- [Niveles de acceso en Visual Basic](access-levels.md)
- [Tipos de datos](../data-types/index.md)
- [Declaración de variable](../variables/variable-declaration.md)
