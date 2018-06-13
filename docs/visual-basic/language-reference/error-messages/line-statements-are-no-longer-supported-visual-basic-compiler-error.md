---
title: '&#39;Línea&#39; instrucciones ya no son compatibles (Error del compilador de Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 06bba0ebfc2faec24f4720c45de3bdcfec993499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587884"
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39;Línea&#39; instrucciones ya no son compatibles (Error del compilador de Visual Basic)
Ya no se admiten instrucciones de línea. Funcionalidad de E/S de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine`.  
  
 **Id. de error:** BC30830  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si está ejecutando el acceso a archivos, utilice `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Si está realizando gráficos, utilice `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
