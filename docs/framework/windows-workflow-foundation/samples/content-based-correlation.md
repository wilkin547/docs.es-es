---
title: "Correlaci&#243;n basada en contenidos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Correlaci&#243;n basada en contenidos
En este ejemplo se muestra cómo las actividades de mensajería \(<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>\) se pueden utilizar con varias correlaciones basadas en contenido y con una correlación basada en contenido.En este escenario, en primer lugar se inicializa una correlación en función de un identificador de pedido de compra y, a continuación, se crea otra correlación basada en el identificador del cliente.Así se muestra cómo una actividad <xref:System.ServiceModel.Activities.Receive> puede seguir una correlación existente e inicializar una nueva correlación basada en el mismo mensaje de entrada.  
  
## Demostraciones  
 Actividades de mensajería y correlación basada en contenido  
  
## Análisis  
 En este ejemplo se muestra cómo utilizar varias correlaciones basadas en contenido.En este escenario, en primer lugar se inicializa una correlación en función de un identificador de pedido de compra y, a continuación, se crea otra correlación basada en el identificador del cliente.Las correlaciones se colocan en cascada utilizando una actividad <xref:System.ServiceModel.Activities.Receive> que sigue una correlación existente \(PurchaseOrderId\) e inicializa una nueva correlación \(CustomerId\) en función del mismo mensaje de entrada.Para ello, la actividad <xref:System.ServiceModel.Activities.Receive> utiliza las propiedades <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> y <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.  
  
## Para utilizar este ejemplo  
  
1.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el botón secundario en el icono [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y seleccionando **Ejecutar como administrador**.  
  
2.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución CascadingCorrelation.sln.  
  
3.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
4.  Presione F5 para ejecutar el servidor.  
  
5.  Cuando el servicio está listo y realizando escuchas para los mensajes, en el Explorador de soluciones, haga clic con el botón secundario en el proyecto Cliente y ejecútelo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`  
  
## Vea también