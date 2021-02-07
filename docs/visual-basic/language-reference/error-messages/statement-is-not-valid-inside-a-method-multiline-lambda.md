---
description: 'Más información sobre: BC30024: la instrucción no es válida dentro de un método o una expresión lambda de varias líneas'
title: Instrucción no válida dentro de un método o una expresión lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: c70e5563ab8c161966cd9790ae1f192fa5d50b17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731180"
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
