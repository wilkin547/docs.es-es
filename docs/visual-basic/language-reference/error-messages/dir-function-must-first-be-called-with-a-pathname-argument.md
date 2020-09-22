---
title: Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1064a44f7c266b9dcce05dfddedef6bb1e919999
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874465"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Se debe llamar primero a la función 'Dir' con un argumento 'Pathname'

Una llamada inicial a la `Dir` función no incluye el `PathName` argumento. La primera llamada a `Dir` debe incluir `PathName` , pero las llamadas subsiguientes a no `Dir` necesitan incluir parámetros para recuperar el elemento siguiente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Proporcione un `PathName` argumento en la llamada de función.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
