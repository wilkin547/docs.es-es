---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: c7a3e6bcd0db268a0e0acfc74c570e26f89cff6a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339078"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
Ya no se admiten instrucciones de línea. Funcionalidad de E/S de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine`.  
  
 **Identificador de error:** BC30830  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Si realiza el acceso a archivos, utilice `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2. Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO>
- <xref:System.Drawing>
- [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
