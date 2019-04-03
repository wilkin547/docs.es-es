---
title: Convención de llamada a archivo DLL no válida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: c4f9917a7fb807cf7da92a3bba2d3edec8045bd2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813525"
---
# <a name="bad-dll-calling-convention"></a>Convención de llamada a archivo DLL no válida
Los argumentos pasados a una biblioteca de vínculos dinámicos (DLL) deben coincidir exactamente con los esperados por la rutina. Convenciones de llamada ocupan de número, tipo y orden de los argumentos. El programa puede estar llamando a una rutina en un archivo DLL que se pasa el tipo incorrecto o el número de argumentos.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que todos los tipos de argumento coinciden con los especificados en la declaración de la rutina que está llamando.  
  
2.  Asegúrese de que está pasando el mismo número de argumentos indicada en la declaración de la rutina que está llamando.  
  
3.  Si la rutina de la DLL espera argumentos por valor, asegúrese de que `ByVal` se especifica para esos argumentos en la declaración de la rutina.  
  
## <a name="see-also"></a>Vea también

- [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Call (instrucción)](../../../visual-basic/language-reference/statements/call-statement.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
