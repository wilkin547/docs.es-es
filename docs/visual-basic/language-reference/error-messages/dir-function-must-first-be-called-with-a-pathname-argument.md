---
title: '&#39;Dir&#39; primero se debe llamar la función con un &#39;PathName&#39; argumento'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518493"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39; primero se debe llamar la función con un &#39;PathName&#39; argumento
Una llamada inicial a la `Dir` función no incluye el `PathName` argumento. La primera llamada a `Dir` debe incluir un `PathName`, las llamadas posteriores, pero a `Dir` no es necesario incluir parámetros para recuperar el elemento siguiente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Proporcione un `PathName` argumento en la llamada de función.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
