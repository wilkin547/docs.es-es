---
title: "&#39; AddressOf &#39; operando debe ser el nombre de un método (sin paréntesis)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39; AddressOf &#39; operando debe ser el nombre de un método (sin paréntesis)
El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico. La sintaxis es la siguiente.  
  
 `AddressOf` `procedurename`  
  
 Inserta el siguiente argumento entre paréntesis `AddressOf`, donde se necesita ninguno.  
  
 **Id. de error:** BC30577  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Quite los paréntesis que rodean el siguiente argumento `AddressOf`.  
  
2.  Asegúrese de que el argumento es un nombre de método.  
  
## <a name="see-also"></a>Vea también  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
