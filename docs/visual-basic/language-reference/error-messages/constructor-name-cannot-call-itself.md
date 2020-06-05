---
title: El constructor '<name>' no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 6abb6dde624e129b52fefecf8c51e6cde2567ae1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409808"
---
# <a name="constructor-name-cannot-call-itself"></a>El constructor '\<name>' no se puede llamar a sí mismo
Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.  
  
 El propósito de un constructor es inicializar una instancia de una clase o estructura cuando se crea por primera vez. Una clase o estructura puede tener varios constructores, siempre que todos tengan listas de parámetros diferentes. Se permite a un constructor llamar a otro constructor para realizar su funcionalidad además de la suya propia. Pero no tiene sentido que un constructor se llame a sí mismo y, de hecho, daría como resultado una recursividad infinita si se permitiera.  
  
 **Identificador de error:** BC30298  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe la lista de parámetros del constructor al que se está llamando. Debe ser diferente del constructor que realiza la llamada.  
  
2. Si no desea llamar a un constructor diferente, quite la llamada por `Sub New` completo.  
  
## <a name="see-also"></a>Consulte también

- [Duración de los objetos: cómo se crean y destruyen](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
