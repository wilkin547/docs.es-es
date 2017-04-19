---
title: "El operando &quot;AddressOf&quot; debe ser el nombre de un método (sin paréntesis) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 04103fe23ee55bb751d9604ef74614edeead8886
ms.lasthandoff: 03/13/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)
El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico. La sintaxis es como sigue.  
  
 `AddressOf` `procedurename`  
  
 Inserte el siguiente argumento entre paréntesis `AddressOf`, cuando no son necesarios.  
  
 **Id. de error:** BC30577  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Quite los paréntesis que rodean el argumento que sigue `AddressOf`.  
  
2.  Asegúrese de que el argumento es un nombre de método.  
  
## <a name="see-also"></a>Vea también  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
