---
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 7f8191b0ef5452fcf6f3a20c3e0f28ca84ef9c4a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163433"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'

Una llamada inicial a la `Dir` función no incluye el `PathName` argumento. La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.

## <a name="to-correct-this-error"></a>Para corregir este error

- Proporcione un `PathName` argumento en la llamada de función.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
