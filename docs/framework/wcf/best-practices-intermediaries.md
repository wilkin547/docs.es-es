---
title: "Procedimientos recomendados: Intermediarios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Procedimientos recomendados: Intermediarios
Se debe tener cuidado en tratar los errores correctamente al llamar a intermediarios para asegurarse de que los canales del lado servicio en el intermediario se cierran correctamente.  
  
 Considere el escenario siguiente.Un cliente realiza una llamada a un intermediario que, a continuación, llamada a un servicio back\-end.El servicio back\-end define un contrato sin errores, por lo que cualquier error que genere el servicio se tratará como un error sin tipo.El servicio back\-end genera <xref:System.ApplicationException> y WCF anula correctamente el canal del lado servicio.<xref:System.ApplicationException> manifiesta <xref:System.ServiceModel.FaultException> que se genera para el intermediario.El intermediario vuelve a generar <xref:System.ApplicationException>.WCF lo interpreta como un error sin tipo procedente del intermediario y lo reenvía al cliente.Después de recibir el error, tanto el intermediario como el cliente generan un error de sus canales del lado cliente.No obstante, el canal del lado servicio del intermediario permanece abierto porque WCF no sabe que el error es grave.  
  
 El procedimiento recomendado en este escenario es detectar si el error que procede del servicio es grave y, en caso afirmativo, el intermediario debe generar el error de su canal del lado servicio tal como se muestra en el siguiente fragmento de código.  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    Else  
    {  
        throw;  
    }  
}  
  
```  
  
## Vea también  
 [Control de errores de WCF](../../../docs/framework/wcf/wcf-error-handling.md)   
 [Especificación y administración de errores en contratos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)