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
ms.openlocfilehash: fa9a1942903dff6f673d87b67ebcad047a410425
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624787"
---
# <a name="stop-statement-visual-basic"></a>Stop (Instrucción, Visual Basic)
Suspende la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución. Mediante el `Stop` instrucción es similar a la configuración de un punto de interrupción en el código.  
  
 El `Stop` instrucción suspende la ejecución, pero, a diferencia `End`, no cierre los archivos ni borrar las variables, a menos que se encuentre en un archivo ejecutable compilado (.exe).  
  
> [!NOTE]
>  Si el `Stop` instrucción se encuentra en el código que se ejecuta fuera del entorno de desarrollo integrado (IDE), se invoca el depurador. Esto es cierto independientemente de si se ha compilado el código en modo de depuración o comercial.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `Stop` instrucción suspenda la ejecución para cada iteración a través de la `For...Next` bucle.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
