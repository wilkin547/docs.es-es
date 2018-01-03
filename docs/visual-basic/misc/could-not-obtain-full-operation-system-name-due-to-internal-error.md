---
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c67d47126718c3d90d853add61b7d06aaf84fc70
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>No se pudo obtener el nombre completo del sistema operativo debido a un error interno
No se pudo obtener el nombre completo del sistema operativo debido a un error interno. La causa podría ser que WMI no exista en la máquina actual.  
  
 Error al llamar a la propiedad `My.Computer.Info.OSFullName` . Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .  
  
2.  Para obtener más información acerca de WMI y cómo instalarlo, vaya a y buscan "Windows Management Instrumentation Core".  
  
## <a name="see-also"></a>Vea también  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [Excepciones y control de errores en Visual Basic](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Try...Catch...Finally (instrucción)](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
