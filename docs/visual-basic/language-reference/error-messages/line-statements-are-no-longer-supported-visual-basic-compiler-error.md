---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 4ca1538dbde0d585b7b421d60cde4531c00e9145
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873836"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)

Ya no se admiten instrucciones de línea. La funcionalidad de e/s de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine` .  
  
 **Identificador de error:** BC30830  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Si se realiza el acceso a archivos, use `Microsoft.VisualBasic.FileSystem.LineInput` .  
  
2. Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IO>
- <xref:System.Drawing>
- [Acceso a archivos con Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
