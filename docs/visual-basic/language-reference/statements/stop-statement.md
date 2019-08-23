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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957619"
---
# <a name="stop-statement-visual-basic"></a>Stop (Instrucción, Visual Basic)
Suspende la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Comentarios  
 Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución. El uso `Stop` de la instrucción es similar al establecimiento de un punto de interrupción en el código.  
  
 La `Stop` instrucción suspende la ejecución, pero, a `End`diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.  
  
> [!NOTE]
> Si la `Stop` instrucción se encuentra en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador. Esto es así independientemente de si el código se compiló en modo de depuración o comercial.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se `Stop` utiliza la instrucción para suspender la ejecución de `For...Next` cada iteración a través del bucle.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Vea también

- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
