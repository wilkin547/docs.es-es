---
title: "Stop (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b7f04214234837a86bf0c77c0d7b6934e2babd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="stop-statement-visual-basic"></a>Stop (Instrucción, Visual Basic)
Suspende la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución. Mediante el `Stop` instrucción es similar a establecer un punto de interrupción en el código.  
  
 El `Stop` instrucción suspende la ejecución, pero, a diferencia `End`, no cierra ningún archivo ni borra variables, a menos que se encuentra en un archivo ejecutable compilado (.exe).  
  
> [!NOTE]
>  Si el `Stop` instrucción se encuentra en código que se ejecuta fuera del entorno de desarrollo integrado (IDE), se invoca el depurador. Esto es cierto independientemente de si el código se compiló en modo de depuración o minorista.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `Stop` instrucción para suspender la ejecución para cada iteración a través de la `For...Next` bucle.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
