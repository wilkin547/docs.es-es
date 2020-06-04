---
title: Instrucción Stop
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
ms.openlocfilehash: 2ef1e2f9045e5509e11557c9fdaf3edd2786b72c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404231"
---
# <a name="stop-statement-visual-basic"></a>Stop (Instrucción, Visual Basic)
Suspende la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Observaciones  
 Puede colocar `Stop` instrucciones en cualquier parte de los procedimientos para suspender la ejecución. El uso de la `Stop` instrucción es similar al establecimiento de un punto de interrupción en el código.  
  
 La `Stop` instrucción suspende la ejecución, pero, `End` a diferencia de, no cierra ningún archivo ni borra ninguna variable, a menos que se encuentre en un archivo ejecutable (. exe) compilado.  
  
> [!NOTE]
> Si la `Stop` instrucción se encuentra en el código que se está ejecutando fuera del entorno de desarrollo integrado (IDE), se invoca al depurador. Esto es así independientemente de si el código se compiló en modo de depuración o comercial.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza la `Stop` instrucción para suspender la ejecución de cada iteración a través del `For...Next` bucle.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Consulte también

- [End (instrucción)](end-statement.md)
