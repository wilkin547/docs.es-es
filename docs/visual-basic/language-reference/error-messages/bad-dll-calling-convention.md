---
title: Convención de llamada a archivo DLL no válida
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: a60e44ce92b1805b0a5a6f1d4ce397c295eef202
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409886"
---
# <a name="bad-dll-calling-convention"></a>Convención de llamada a archivo DLL no válida
Los argumentos pasados a una biblioteca de vínculos dinámicos (DLL) deben coincidir exactamente con los esperados por la rutina. Las convenciones de llamada abordan el número, el tipo y el orden de los argumentos. Es posible que el programa esté llamando a una rutina de un archivo DLL al que se está pasando el tipo o el número de argumentos equivocado.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que todos los tipos de argumento coinciden con los especificados en la declaración de la rutina a la que está llamando.  
  
2. Asegúrese de que está pasando el mismo número de argumentos indicado en la declaración de la rutina a la que está llamando.  
  
3. Si la rutina DLL espera argumentos por valor, asegúrese de que `ByVal` se especifica para esos argumentos en la declaración de la rutina.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de error](../../programming-guide/language-features/error-types.md)
- [Instrucción Call](../statements/call-statement.md)
- [Declare Statement](../statements/declare-statement.md)
