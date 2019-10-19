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
ms.openlocfilehash: e9382ee34842fc3a3b4b23f71848bda602c99780
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583216"
---
# <a name="stop-statement-visual-basic"></a>Stop (Instrucción, Visual Basic)
Suspende la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución. El uso de la instrucción `Stop` es similar al establecimiento de un punto de interrupción en el código.  
  
 La instrucción `Stop` suspende la ejecución, pero a diferencia de `End`, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.  
  
> [!NOTE]
> Si se encuentra la instrucción `Stop` en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador. Esto es así independientemente de si el código se compiló en modo de depuración o comercial.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza la instrucción `Stop` para suspender la ejecución de cada iteración a través del bucle `For...Next`.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Vea también

- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
