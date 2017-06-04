---
title: "Retraso duradero en XAMLX | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Retraso duradero en XAMLX
En este ejemplo se muestra cómo utilizar un retraso duradero, que es un retraso que conserva el flujo de trabajo en un dispositivo duradero durante el tiempo que dura.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## Análisis  
 El flujo de trabajo de muestra contiene dos mensajes a un archivo local, separados por un retraso.Cuando el retraso se activa, el flujo de trabajo se descarga y espera 5 segundos en el almacén de instancias de flujo de trabajo antes de recargarse en la memoria.  
  
 El archivo .xamlx es un servicio de flujo de trabajo hospedado en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] usa Cassini que usa un host de servicio de flujo de trabajo para hospedar el flujo de trabajo.  
  
 Además de hospedar el flujo de trabajo, el host de servicio de flujo de trabajo administra las instancias de flujo de trabajo cargándolas y descargándolas.Para iniciar una instancia de la definición de [!INCLUDE[wf](../../../../includes/wf-md.md)] \(en el host de servicio de flujo de trabajo\), establezca un cliente que envíe un mensaje a la actividad <xref:System.ServiceModel.Activities.Receive> en el flujo de trabajo.<xref:System.ServiceModel.Activities.Receive> tiene su propiedad <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> establecida en `true`, lo que le permite crear una nueva instancia del flujo de trabajo después de recibir un mensaje.  
  
 Durante la inicialización, se agrega un comportamiento de instancia de descarga al archivo de configuración que especifica al host de servicio de flujo de trabajo en el que debe descargarse una instancia al almacén de persistencia \(base de datos\).En este ejemplo, descarga la instancia de forma inmediata cuando el flujo de trabajo pasa a estado inactivo \(cuando el retraso se activa\).  
  
#### Para utilizar este ejemplo  
  
1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Navegue hasta la carpeta DurableDelayXamlx\\CS.  
  
3.  Ejecute Setup.cmd.  
  
4.  Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] como administrador.  
  
5.  Abra el archivo de solución DurableDelayXamlx.sln.  
  
6.  En el **Explorador de soluciones**, haga clic con el botón secundario en la solución y seleccione **Propiedades**.  
  
7.  Seleccione **Proyectos de inicio múltiples** y establezca ambos proyectos en **Iniciar**.  
  
8.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
9. Para ejecutar la solución, presione CTRL\+F5.  
  
#### Para desinstalar este ejemplo  
  
1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Navegue hasta la carpeta DurableDelayXamlx\\CS.  
  
3.  Ejecute Cleanup.cmd.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`