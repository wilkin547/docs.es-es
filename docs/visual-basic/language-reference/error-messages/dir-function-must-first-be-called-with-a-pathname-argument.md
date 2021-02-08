---
description: "Obtenga más información sobre: la función dir ' debe llamarse primero con un argumento ' PathName '"
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: ee492a269d41e8c9fe1fddbd59210b59fbe8618c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796592"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'

Una llamada inicial a la `Dir` función no incluye el `PathName` argumento. La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.

## <a name="to-correct-this-error"></a>Para corregir este error

- Proporcione un `PathName` argumento en la llamada de función.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
