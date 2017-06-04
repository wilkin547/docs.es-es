---
title: "Servicios (flujo de trabajo de Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 521cdb66-98cb-4ad1-b706-370788a43485
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Servicios (flujo de trabajo de Windows)
Esta sección contiene ejemplos que muestran escenarios mediante servicios de flujo de trabajo.  
  
## En esta sección  
 [OperationScope](../../../../docs/framework/windows-workflow-foundation/samples/operationscope.md)  
 Muestra cómo las actividades de mensajería, <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>, se pueden utilizar para exponer una actividad personalizada existente como una operación en un servicio de flujo de trabajo.  
  
 [Obtener acceso a OperationContext](../../../../docs/framework/windows-workflow-foundation/samples/accessing-operationcontext.md)  
 Muestra cómo se pueden utilizar las actividades de mensajería \(<xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.Send>\) con una actividad de ámbito personalizada para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A> y adjuntar o recuperar un encabezado de mensaje personalizado dentro de un mensaje de salida o entrante.  
  
 [Correlación de consultas de mensajes LINQ](../../../../docs/framework/windows-workflow-foundation/samples/linq-message-query-correlation.md)  
 Muestra cómo realizar una correlación basada en contenidos mediante una implementación de <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizada en contraposición a <xref:System.ServiceModel.XPathMessageQuery> proporcionado por el sistema.  
  
 [Calculadora correlacionada](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)  
 Muestra cómo utilizar las actividades de mensajería \(<xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>\) en el diseñador con correlación basada en contenidos en función de un parámetro en el mensaje.  
  
 [Proteger servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/samples/securing-workflow-services.md)  
 Muestra cómo crear un servicio del flujo de trabajo básico mediante las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> y utilizando la configuración [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para definir extremos seguros para que los utilice el servicio del flujo de trabajo.  
  
 [Comunicación asincrónica](../../../../docs/framework/windows-workflow-foundation/samples/asynchronous-communication.md)  
 Muestra cómo se realiza de forma predeterminada la comunicación entre dos servicios de [!INCLUDE[wf](../../../../includes/wf-md.md)] diferentes de forma asincrónica.