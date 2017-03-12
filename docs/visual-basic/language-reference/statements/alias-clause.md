---
title: "Alias (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Alias"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Alias (palabra clave)"
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Alias (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica que un procedimiento externo tiene un nombre diferente en su archivo DLL.  
  
## Comentarios  
 La palabra clave `Alias` se puede utilizar en este contexto:  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 En el ejemplo siguiente, la palabra clave `Alias` se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA`, en cuyo lugar se usa `getUserName` en este ejemplo.  Se llama a la función `getUserName` en el subproceso `getUser`, que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/alias-clause_1.vb)]  
  
## Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)