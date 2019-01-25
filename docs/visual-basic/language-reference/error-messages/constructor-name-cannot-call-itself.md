---
title: Constructor &#39; &lt;nombre&gt; &#39; no se puede llamar a sí mismo
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 4a02277893147716098a3dcc327e221e0775d476
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662730"
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>Constructor &#39; &lt;nombre&gt; &#39; no se puede llamar a sí mismo
Un `Sub New` procedimiento en una clase o estructura se llama a sí mismo.  
  
 Es el propósito de un constructor inicializar una instancia de una clase o estructura cuando sea primera creado. Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes. Se permite un constructor para llamar a otro constructor para llevar a cabo su funcionalidad además de su propio. Pero no tiene sentido que un constructor llame a sí mismo y de hecho el resultado sería una recursividad infinita si lo permite.  
  
 **Identificador de error:** BC30298  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe la lista de parámetros del constructor que se llama. Debe ser diferente de la que realiza la llamada de constructor.  
  
2.  Si no piensa llamar a un constructor diferente, quite el `Sub New` llamar por completo.  
  
## <a name="see-also"></a>Vea también
- [Duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
