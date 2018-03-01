---
title: Las clases derivadas no pueden provocar eventos de clase base
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70dde8b96980adfd618e38b9ce142cdec56a6b13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Las clases derivadas no pueden provocar eventos de clase base
Un evento se puede generar solo desde el espacio de declaración en el que se declara. Por lo tanto, una clase no puede provocar los eventos de cualquier otra clase, incluso uno del que se deriva.  
  
 **Id. de error:** BC30029  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mover el `Event` instrucción o `RaiseEvent` instrucción para que estén en la misma clase.  
  
## <a name="see-also"></a>Vea también  
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)  
 [RaiseEvent (instrucción)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
