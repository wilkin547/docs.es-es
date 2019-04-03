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
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827996"
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
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Vea también

- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
