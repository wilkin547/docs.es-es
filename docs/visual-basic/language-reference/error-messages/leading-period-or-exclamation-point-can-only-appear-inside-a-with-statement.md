---
title: "Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39; Con &#39; instrucción"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a>Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39; Con &#39; instrucción
Un punto (.) o un signo de exclamación (!) que no está dentro un `With` bloqueo se produce sin una expresión de la izquierda. Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro. Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.  
  
 **Id. de error:** BC30157  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que el `With` bloque tiene el formato correcto.  
  
2.  Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.  
  
## <a name="see-also"></a>Vea también  
 [Caracteres especiales en el código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [With...End With (instrucción)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
