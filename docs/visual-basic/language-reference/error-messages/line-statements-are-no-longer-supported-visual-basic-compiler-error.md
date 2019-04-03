---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 7616bcdc39ab479049586534fac22f1e2d96a700
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831844"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
Ya no se admiten instrucciones de línea. Funcionalidad de E/S de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine`.  
  
 **Identificador de error:** BC30830  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si realiza el acceso a archivos, utilice `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO>
- <xref:System.Drawing>
- [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
