---
title: Stop (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599140"
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
