---
title: La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New' (constructor no accesible sin parámetros)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: e336494ad78e9835f62ad54bb4dbf91a63172a25
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874104"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a>La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New' (constructor no accesible sin parámetros)

La primera instrucción de este ' Sub New ' debe ser una llamada a ' MyBase. New ' o ' MyClass. New ' porque la clase base ' \<basename> ' de ' \<derivedname> ' no tiene un ' Sub New ' accesible al que se pueda llamar sin argumentos.  
  
 En una clase derivada, cada constructor debe llamar a un constructor de clase base ( `MyBase.New` ). Si la clase base tiene un constructor sin parámetros que es accesible para las clases derivadas, `MyBase.New` se puede llamar a de forma automática. Si no es así, se debe llamar a un constructor de clase base con parámetros y no se puede hacer de forma automática. En este caso, la primera instrucción de cada constructor de clase derivada debe llamar a un constructor con parámetros en la clase base, o llamar a otro constructor de la clase derivada que realiza una llamada a un constructor de clase base.  
  
 **Identificador de error:** BC30148  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Llame a para `MyBase.New` proporcionar los parámetros necesarios o llame a un constructor del mismo nivel que realice esta llamada.  
  
     Por ejemplo, si la clase base tiene un constructor declarado como `Public Sub New(ByVal index as Integer)` , la primera instrucción del constructor de la clase derivada podría ser `MyBase.New(100)` .  
  
## <a name="see-also"></a>Consulte también

- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
