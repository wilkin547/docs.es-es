---
title: '&#39;Dir&#39; en primer lugar debe llamar la función con un &#39;PathName&#39; argumento'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585465"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39; en primer lugar debe llamar la función con un &#39;PathName&#39; argumento
Una llamada inicial a la `Dir` función no incluye la `PathName` argumento. La primera llamada a `Dir` debe incluir un `PathName`, pero posteriores llamadas a `Dir` no es necesario incluir parámetros para recuperar el elemento siguiente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Proporcione un `PathName` argumento en la llamada de función.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
