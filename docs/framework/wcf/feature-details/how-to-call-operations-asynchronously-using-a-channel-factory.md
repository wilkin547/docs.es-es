---
title: "C&#243;mo llamar a operaciones de manera asincr&#243;nica mediante un generador de canales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# C&#243;mo llamar a operaciones de manera asincr&#243;nica mediante un generador de canales
En este tema se cubre cómo un cliente puede obtener acceso de forma asincrónica a una operación del servicio al utilizar una aplicación de cliente basada en <xref:System.ServiceModel.ChannelFactory%601>.  \(Al utilizar un objeto <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> para invocar un servicio, puede utilizar el modelo de llamada asincrónica orientado a eventos.  Para obtener más información, consulta [Cómo: Llamar a operaciones de servicio de forma asincrónica](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  Para obtener más información sobre el modelo de llamada asincrónica basada en eventos, vea [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)\).  
  
 El servicio en este tema implementa la interfaz `ICalculator`.  El cliente puede llamar a las operaciones en esta interfaz de forma asincrónica, lo que significa que las operaciones como `Add` se dividen en dos métodos, `BeginAdd` y `EndAdd`, de los cuales el primero inicia la llamada y el segundo recupera el resultado cuando la operación termina.  Para obtener un ejemplo que muestra cómo implementar de forma asincrónica una operación en un servicio, vea [Cómo: Implementar una operación de servicios asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).  Para obtener información detallada de las operaciones sincrónicas y asincrónicas, vea [Operaciones sincrónicas y asincrónicas](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
## Procedimiento  
  
#### Para llamar a operaciones de servicio WCF de forma asincrónica  
  
1.  Ejecute la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con la opción `/async` tal y como se muestra en el comando siguiente.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
  
    ```  
  
     Esto genera una versión de cliente asincrónica del contrato de servicio para la operación.  
  
2.  Cree una función de devolución de llamada a la que se va a llamar cuando la operación asincrónica haya finalizado, tal y como aparece en el siguiente código de ejemplo.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  Para obtener acceso de forma asincrónica a una operación de servicio, cree el cliente y llame a `Begin[Operation]` \(por ejemplo, `BeginAdd`\) y especifique una función de devolución de llamada, tal y como se muestra en el siguiente código de ejemplo.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     Cuando la función de devolución de llamada se ejecuta, el cliente llama a `End<operation>``EndAdd` \(por ejemplo, \) para recuperar el resultado.  
  
## Ejemplo  
 El servicio que se usa con el código de cliente que se utiliza en el procedimiento anterior implementa la interfaz `ICalculator` tal y como se muestra en el código siguiente.  En el lado del servicio, el tiempo de ejecución de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] invoca de manera sincrónica a las operaciones `Add` y `Subtract` del contrato, aunque los pasos precedentes del cliente se invoquen de manera asincrónica en el cliente.  Las operaciones `Divide` y `Multiply` se utilizan para invocar de forma asincrónica el servicio en el lado del servicio, incluso aunque el cliente los invoque de forma sincrónica.  Este ejemplo establece la propiedad <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> en `true`.  Este valor de la propiedad, en combinación con la implementación del patrón asincrónico [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], indica al tiempo de ejecución para invocar la operación de forma asincrónica.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## Vea también  
 [Service Contract: Asynchronous Sample](http://msdn.microsoft.com/es-es/833db946-f511-4f64-a26f-2759a11217c7)