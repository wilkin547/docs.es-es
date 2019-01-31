---
title: El constructor '<name>' no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 67933e9365b1aa18063f0ccf3c2146a261e7eafc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276047"
---
# <a name="constructor-name-cannot-call-itself"></a>Constructor '\<nombre >' no se puede llamar a sí mismo
Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.  
  
 Es el propósito de un constructor inicializar una instancia de una clase o estructura cuando sea primera creado. Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes. Se permite un constructor para llamar a otro constructor para llevar a cabo su funcionalidad además de su propio. Pero no tiene sentido que un constructor llame a sí mismo y de hecho el resultado sería una recursividad infinita si lo permite.  
  
 **Identificador de error:** BC30298  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe la lista de parámetros del constructor que se llama. Debe ser diferente de la que realiza la llamada de constructor.  
  
2.  Si no piensa llamar a un constructor diferente, quite el `Sub New` llamar por completo.  
  
## <a name="see-also"></a>Vea también
- [Duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
