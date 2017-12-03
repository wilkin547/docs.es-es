---
title: Cargar de XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 54acfb1a130c8a790411a05958518665ef790e53
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="load-from-xaml"></a>Cargar de XAML
En este ejemplo se muestra cómo cargar dinámicamente un flujo de trabajo de XAML sin tener que ejecutar la herramienta XamlBuildTask. En su lugar, el ejemplo llama al método <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>. El ejemplo es una aplicación cliente de [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] que carga flujos de trabajo de XAML mediante la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices> y los ejecuta. Una vez cargados utilizando la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices>, se devuelve una actividad <xref:System.Activities.DynamicActivity%601> que se puede ejecutar.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LoadFromXAML.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`