---
title: "Codificador de ByteStream | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Codificador de ByteStream
Este ejemplo muestra cómo crear un objeto `ByteStreamHttpBinding`, <xref:System.ServiceModel.Channels.Binding> que ilustra la funcionalidad del codificador del flujo de bytes.  
  
## Explicación  
 En este ejemplo se muestra cómo crear un objeto <xref:System.ServiceModel.Channels.Binding> estándar mediante los elementos de enlace estándar <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.  En este ejemplo se muestra cómo utilizar el codificador de flujo de bytes para cargar y descargar una imagen.  La característica de codificador de flujo de bytes solo admite el transporte HTTP y no admite características como la mensajería de confianza o la seguridad.  La única <xref:System.ServiceModel.Channels.MessageVersion> que se admite es la propiedad <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
> [!IMPORTANT]
>  Si va a ejecutar este ejemplo en [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], asegúrese de que va a ejecutar [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegios elevados.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra el archivo ByteStreamHttpBinding.sln en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Inicie una nueva instancia del proyecto ByteStreamHttpBindingServer haciendo clic con el botón secundario en el proyecto, en el Explorador de soluciones, seleccionando **Depuración** y, a continuación, **Iniciar nueva instancia** desde el menú contextual.  
  
3.  Inicie una nueva instancia del proyecto ByteStreamHttpBindingClient haciendo clic con el botón secundario en el proyecto, en el Explorador de soluciones, seleccionando **Depuración** y, a continuación, **Iniciar nueva instancia** desde el menú contextual.