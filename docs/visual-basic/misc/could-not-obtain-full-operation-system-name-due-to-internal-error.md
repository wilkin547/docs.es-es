---
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 67e8fb5e906800d28bf15714463b7ff6ae585693
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402283"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>No se pudo obtener el nombre completo del sistema operativo debido a un error interno
No se pudo obtener el nombre completo del sistema operativo debido a un error interno. La causa podría ser que WMI no exista en la máquina actual.  
  
 Error al llamar a la propiedad `My.Computer.Info.OSFullName` . Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .  
  
2. Para obtener más información acerca de WMI y cómo instalarlo, vaya a y busque "Instrumental de administración de Windows Core".  
  
## <a name="see-also"></a>Consulte también

- [My. Computer. info. OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [Controlar y generar excepciones en .NET](../../standard/exceptions/index.md)
- [Instrucción Try...Catch...Finally](../language-reference/statements/try-catch-finally-statement.md)
