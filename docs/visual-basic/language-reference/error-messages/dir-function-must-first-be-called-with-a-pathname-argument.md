---
title: "&#39; Dir &#39; en primer lugar debe llamar la función con un &#39; Ruta de acceso &#39; argumento"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 843918fe9cb0b9dece076b5dc1373c3571588caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39; Dir &#39; en primer lugar debe llamar la función con un &#39; Ruta de acceso &#39; argumento
Una llamada inicial a la `Dir` función no incluye la `PathName` argumento. La primera llamada a `Dir` debe incluir un `PathName`, pero posteriores llamadas a `Dir` no es necesario incluir parámetros para recuperar el elemento siguiente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Proporcione un `PathName` argumento en la llamada de función.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
