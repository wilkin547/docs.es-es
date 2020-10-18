---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: f34095becf321c6cb4b316b6378a2da0107577ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162484"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a>BC30830: ya no se admiten instrucciones ' line '

Ya no se admiten instrucciones de línea. La funcionalidad de e/s de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine` .

 **Identificador de error:** BC30830

## <a name="to-correct-this-error"></a>Para corregir este error

- Si se realiza el acceso a archivos, use `Microsoft.VisualBasic.FileSystem.LineInput` .

- Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.

## <a name="see-also"></a>Vea también

- <xref:System.IO>
- <xref:System.Drawing>
- [Acceso a archivos con Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
