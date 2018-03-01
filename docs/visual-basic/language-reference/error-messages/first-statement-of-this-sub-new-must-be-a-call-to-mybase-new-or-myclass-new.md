---
title: "La primera instrucción de este &#39; Sub New &#39; debe ser una llamada a &#39; MyBase.New &#39; o &#39; MyClass.New &#39; (Ningún Constructor accesible sin parámetros)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1065643e1f6c868092fbad839af0dbbd33afaf01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a>La primera instrucción de este &#39; Sub New &#39; debe ser una llamada a &#39; MyBase.New &#39; o &#39; MyClass.New &#39; (Ningún Constructor accesible sin parámetros)
La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New' porque clase base\<basename >' de '\<derivedname >' no tiene un 'Sub New' accesible que se pueda llamar sin argumentos.  
  
 En una clase derivada, cada constructor debe llamar a un constructor de clase base (`MyBase.New`). Si la clase base tiene un constructor sin parámetros accesible para las clases derivadas, `MyBase.New` puede llamarse automáticamente. De lo contrario, debe llamar a un constructor de clase base con parámetros y no puede hacerlo automáticamente. En este caso, la primera instrucción de cada constructor de clase derivada debe llamar a un constructor con parámetros en la clase base, o llamar a otro constructor de la clase derivada que realiza un constructor de clase base llamada.  
  
 **Id. de error:** BC30148  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Llamar a `MyBase.New` indicando los parámetros necesarios, o llamar a un constructor del mismo nivel que realiza una llamada de este tipo.  
  
     Por ejemplo, si la clase base tiene un constructor que se declara como `Public Sub New(ByVal index as Integer)`, la primera instrucción de la clase derivada podría ser el constructor de clase `MyBase.New(100)`.  
  
## <a name="see-also"></a>Vea también  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
