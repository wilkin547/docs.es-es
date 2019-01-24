---
title: La primera instrucción de este &#39;Sub New&#39; debe ser una llamada a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; (ningún Constructor accesible sin parámetros)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 75832ae88908094c1cb74ce04ad84c0d2ae91e68
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728900"
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>La primera instrucción de este &#39;Sub New&#39; debe ser una llamada a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; (ningún Constructor accesible sin parámetros)
La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New' porque clase base\<basename >' de '\<derivedname >' no tiene un 'Sub New' accesible que se puede llamar sin argumentos.  
  
 En una clase derivada, cada constructor debe llamar a un constructor de clase base (`MyBase.New`). Si la clase base tiene un constructor sin parámetros accesible para las clases derivadas, `MyBase.New` se puede llamar de forma automática. Si no es así, debe llamar a un constructor de clase base con parámetros y no puede realizarse automáticamente. En este caso, la primera instrucción de cada constructor de clase derivada debe llamar a un constructor con parámetros en la clase base, o llamar a otro constructor en la clase derivada que realiza un constructor de clase base llamada.  
  
 **Identificador de error:** BC30148  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   O bien llamada `MyBase.New` indicando los parámetros necesarios, o llamar a un constructor del mismo nivel que realiza una llamada de este tipo.  
  
     Por ejemplo, si la clase base tiene un constructor que se declara como `Public Sub New(ByVal index as Integer)`, la primera instrucción de la clase derivada podría ser el constructor de clase `MyBase.New(100)`.  
  
## <a name="see-also"></a>Vea también
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
