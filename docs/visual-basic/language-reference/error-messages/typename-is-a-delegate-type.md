---
title: '&#39;&lt;TypeName&gt; &#39; es un tipo delegado'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 6676328d0c1ea459f5934b5f9e2cb66580adad40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737207"
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;TypeName&gt; &#39; es un tipo delegado
'\<typename >' es un tipo delegado. Construcción de delegado permite una única expresión AddressOf como una lista de argumentos. A menudo se puede usar una expresión de AddressOf en lugar de una construcción de delegado.  
  
 Un `New` cláusula crea una instancia de una clase de delegado proporciona una lista de argumentos no válido al constructor de delegado.  
  
 Puede proporcionar una sola `AddressOf` expresión al crear una nueva instancia de delegado.  
  
 Este error puede producirse si no pasa ningún argumento al constructor de delegado, si se pasa más de un argumento, o si se pasa un único argumento que no es válido `AddressOf` expresión.  
  
 **Identificador de error:** BC32008  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Usar una sola `AddressOf` expresión en la lista de argumentos para la clase de delegado en el `New` cláusula.  
  
## <a name="see-also"></a>Vea también
- [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md)
- [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Cómo: Invocar un método delegado](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
