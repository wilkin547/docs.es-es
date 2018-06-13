---
title: Usar una actividad de .NET Framework 3.0 o .NET Framework 3.5 en un flujo de trabajo de .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ab2e93918617bd1ca21fb32878d446db0dd2ef16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514904"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a>Usar una actividad de .NET Framework 3.0 o .NET Framework 3.5 en un flujo de trabajo de .NET Framework 4.5
El <xref:System.Activities.Statements.Interop> actividad le permite ejecutar una actividad de Windows Workflow Foundation (WF) de .NET Framework 3.0 en un [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] flujo de trabajo. En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Interop> para pasar una cadena como un argumento a una actividad de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] personalizada.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo de solución SimpleInterop.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a>Vea también
