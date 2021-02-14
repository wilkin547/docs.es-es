---
description: "Obtenga más información sobre: la función ' dir ' debe llamarse primero con un argumento ' PathName '"
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 076828978b27911a97a4767cde1b1d7b04317a31
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479977"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'

Una llamada inicial a la `Dir` función no incluye el `PathName` argumento. La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.

## <a name="to-correct-this-error"></a>Para corregir este error

- Proporcione un `PathName` argumento en la llamada de función.

## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
