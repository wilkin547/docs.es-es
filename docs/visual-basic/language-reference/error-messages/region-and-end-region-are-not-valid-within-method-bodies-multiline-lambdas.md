---
title: Las instrucciones "#Region" y "#End Region" no son válidas en los cuerpos de método y operaciones lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162289"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>BC32025: las instrucciones ' #Region ' y ' #End region ' no son válidas en cuerpos de método o expresiones lambda de varias líneas

El `#Region` bloque se debe declarar en el nivel de clase, módulo o espacio de nombres. Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni finalizar dentro de un procedimiento.

 **Identificador de error:** BC32025

## <a name="to-correct-this-error"></a>Para corregir este error

1. Asegúrese de que el procedimiento anterior finaliza correctamente con una `End Function` `End Sub` instrucción o.

2. Asegúrese de que `#Region` las `#End Region` directivas y están en el mismo bloque de código.

## <a name="see-also"></a>Vea también

- [#Region (Directiva)](../directives/region-directive.md)
