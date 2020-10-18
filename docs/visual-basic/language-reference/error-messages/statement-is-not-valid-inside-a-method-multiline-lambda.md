---
title: Instrucción no válida dentro de un método o una expresión lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159682"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a>BC30024: la instrucción no es válida dentro de un método o una expresión lambda de varias líneas

La instrucción no es válida dentro de `Sub` un `Function` procedimiento de propiedad,, propiedad `Get` o `Set` . Algunas instrucciones se pueden colocar en el nivel de módulo o de clase. Otros, como `Option Strict` , deben estar en el nivel de espacio de nombres y preceder a todas las demás declaraciones.

 **Identificador de error:** BC30024

## <a name="to-correct-this-error"></a>Para corregir este error

- Quite la instrucción del procedimiento.

## <a name="see-also"></a>Vea también

- [Instrucción Sub](../statements/sub-statement.md)
- [Instrucción Function](../statements/function-statement.md)
- [Get (Instrucción)](../statements/get-statement.md)
- [Set (instrucción)](../statements/set-statement.md)
