---
title: "Cargar de XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Cargar de XAML
En este ejemplo se muestra cómo cargar dinámicamente un flujo de trabajo de XAML sin tener que ejecutar la herramienta XamlBuildTask.En su lugar, el ejemplo llama al método <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>.El ejemplo es una aplicación cliente de [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] que carga flujos de trabajo de XAML mediante la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices> y los ejecuta.Una vez cargados utilizando la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices>, se devuelve una actividad <xref:System.Activities.DynamicActivity%601> que se puede ejecutar.  
  
#### Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LoadFromXAML.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`  
  
## Vea también