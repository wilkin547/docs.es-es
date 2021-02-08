---
description: "Más información sobre: BC30830: las instrucciones ' line ' ya no se admiten"
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 16696856cee365171000e7b0abc206c42d3f3174
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795877"
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
