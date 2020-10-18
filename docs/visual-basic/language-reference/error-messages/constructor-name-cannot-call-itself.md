---
title: El constructor '<name>' no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: f40319cde8388b17e27cfaec2117ebd519ebd4ff
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160950"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a>BC30298: el constructor ' \<name> ' no se puede llamar a sí mismo

Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.

 El propósito de un constructor es inicializar una instancia de una clase o estructura cuando se crea por primera vez. Una clase o estructura puede tener varios constructores, siempre que todos tengan listas de parámetros diferentes. Se permite a un constructor llamar a otro constructor para realizar su funcionalidad además de la suya propia. Pero no tiene sentido que un constructor se llame a sí mismo y, de hecho, daría como resultado una recursividad infinita si se permitiera.

 **Identificador de error:** BC30298

## <a name="to-correct-this-error"></a>Para corregir este error

1. Compruebe la lista de parámetros del constructor al que se está llamando. Debe ser diferente del constructor que realiza la llamada.

2. Si no desea llamar a un constructor diferente, quite la llamada por `Sub New` completo.

## <a name="see-also"></a>Vea también

- [Duración de los objetos: cómo se crean y destruyen](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
