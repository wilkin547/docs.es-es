---
title: "Especificaci&#243;n del comportamiento de tiempo de ejecuci&#243;n del cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "comportamientos [WCF], proporcionada por el sistema cliente"
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Especificaci&#243;n del comportamiento de tiempo de ejecuci&#243;n del cliente
Los clientes [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], como los servicios [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], se pueden configurar para modificar el comportamiento de tiempo de ejecución con el fin de satisfacer la aplicación cliente. Tres atributos están disponibles para especificar el comportamiento de tiempo de ejecución del cliente. Objetos de devolución de llamada de cliente dúplex pueden utilizar el <xref:System.ServiceModel.CallbackBehaviorAttribute> y <xref:System.ServiceModel.Description.CallbackDebugBehavior> atributos para modificar su comportamiento en tiempo de ejecución. El otro atributo <xref:System.ServiceModel.Description.ClientViaBehavior>, puede utilizarse para separar el destino lógico del destino de red inmediato. Además, los tipos de devolución de llamada de cliente dúplex pueden utilizar algunos de los comportamientos de lado del servicio. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Especificación del comportamiento de tiempo de ejecución del servicio](../../../docs/framework/wcf/specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Utilizar CallbackBehaviorAttribute  
 Puede configurar o extender el comportamiento de ejecución de una implementación de contrato de devolución de llamada en una aplicación cliente mediante la <xref:System.ServiceModel.CallbackBehaviorAttribute> clase. Este atributo realiza una función similar para la clase de devolución de llamada como el <xref:System.ServiceModel.ServiceBehaviorAttribute> (clase), con la excepción de configuración de transacción y el comportamiento de creación de instancias.  
  
 El <xref:System.ServiceModel.CallbackBehaviorAttribute> clase se debe aplicar a la clase que implementa el contrato de devolución de llamada. Si se aplica a una implementación de contrato de no dúplex, un <xref:System.InvalidOperationException> se produce una excepción en tiempo de ejecución. El siguiente ejemplo de código muestra un <xref:System.ServiceModel.CallbackBehaviorAttribute> clase en un objeto de devolución de llamada que usa el <xref:System.Threading.SynchronizationContext> objeto para determinar el subproceso para calcular, la <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> propiedad para exigir la validación del mensaje y el <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> propiedad para devolver las excepciones como <xref:System.ServiceModel.FaultException> objetos al servicio con fines de depuración.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Utilizar CallbackDebugBehavior para habilitar el flujo de información de excepción administrada  
 Puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada del cliente al servicio con fines de depuración estableciendo el <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> propiedad `true` archivo mediante programación o desde una configuración de aplicación.  
  
 Devolver la información de excepción administrada a los servicios puede suponer un riesgo para la seguridad porque los datos de la excepción exponen información sobre la implementación del cliente interna que los servicios desautorizados podrían utilizar. Además, aunque la <xref:System.ServiceModel.Description.CallbackDebugBehavior> propiedades también se pueden establecer mediante programación, puede ser fácil olvidarse de deshabilitar <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> al implementar.  
  
 Debido a los problemas de seguridad implicados, se recomienda encarecidamente que:  
  
-   Usar un archivo de configuración para establecer el valor de la <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> propiedad `true`.  
  
-   lo haga solamente en escenarios de depuración controlados.  
  
 El ejemplo de código siguiente muestra un archivo de configuración del cliente que indica a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que devuelva la información de excepción administrada de un objeto de devolución de llamada de cliente en mensajes SOAP.  
  
 <!-- TODO: review snippet reference [!code[SCA.CallbackContract#4](../../../samples/snippets/common/VS_Snippets_CFX/sca.callbackcontract/common/client.exe.config#4)]  -->
 <!-- TODO: review snippet reference [!code-csharp[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  -->
 <!-- TODO: review snippet reference [!code-vb[SCA.CallbackContract#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.callbackcontract/vb/client.exe.config#4)]  -->  
  
## <a name="using-the-clientviabehavior-behavior"></a>Utilizar el comportamiento de ClientViaBehavior  
 Puede usar el <xref:System.ServiceModel.Description.ClientViaBehavior> comportamiento para especificar el identificador uniforme de recursos para el que se debe crear el canal de transporte. Utilice este comportamiento cuando el destino de la red inmediato no es el procesador de impresión previsto del mensaje. Esto habilita conversaciones de varios saltos cuando la aplicación que realiza la llamada no conoce necesariamente el destino último o cuando el encabezado de destino `Via` no es una dirección.  
  
## <a name="see-also"></a>Vea también  
 [Especificar el comportamiento de tiempo de ejecución de servicio](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)