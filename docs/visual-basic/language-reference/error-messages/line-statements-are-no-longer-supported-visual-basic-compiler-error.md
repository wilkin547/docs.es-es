---
title: "&#39; Línea &#39; las instrucciones son ya no se admite (Error del compilador de Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords: BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d2db5dc786749360dfcf6789f12b5659d5713fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39; Línea &#39; las instrucciones son ya no se admite (Error del compilador de Visual Basic)
Ya no se admiten instrucciones de línea. Funcionalidad de E/S de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine`.  
  
 **Id. de error:** BC30830  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si está ejecutando el acceso a archivos, utilice `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Si está realizando gráficos, utilice `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
