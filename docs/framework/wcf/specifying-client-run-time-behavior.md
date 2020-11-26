---
title: Especificación del comportamiento de tiempo de ejecución del cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
ms.openlocfilehash: 17031f2100c6760cd14aae57cd4efab7428eb362
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235901"
---
# <a name="specifying-client-run-time-behavior"></a>Especificación del comportamiento de tiempo de ejecución del cliente

Los clientes de Windows Communication Foundation (WCF), como los servicios de Windows Communication Foundation (WCF), se pueden configurar para modificar el comportamiento de tiempo de ejecución para que se ajuste a la aplicación cliente. Tres atributos están disponibles para especificar el comportamiento de tiempo de ejecución del cliente. Los objetos de devolución de llamada de cliente dúplex pueden utilizar <xref:System.ServiceModel.CallbackBehaviorAttribute> y los atributos <xref:System.ServiceModel.Description.CallbackDebugBehavior> para modificar su comportamiento de tiempo de ejecución. El otro atributo, <xref:System.ServiceModel.Description.ClientViaBehavior>, se puede utilizar para separar el destino lógico del destino de red inmediato. Además, los tipos de devolución de llamada de cliente dúplex pueden utilizar algunos de los comportamientos de lado del servicio. Para obtener más información, vea [especificar el comportamiento de Run-Time de servicio](specifying-service-run-time-behavior.md).  
  
## <a name="using-the-callbackbehaviorattribute"></a>Utilizar CallbackBehaviorAttribute  

 Puede configurar o extender el comportamiento de ejecución de una implementación de contrato de devolución de llamada en una aplicación cliente utilizando la clase <xref:System.ServiceModel.CallbackBehaviorAttribute>. Este atributo realiza una función similar para la clase de devolución de llamada como la clase <xref:System.ServiceModel.ServiceBehaviorAttribute>, con la excepción de crear instancias del comportamiento y configuración de la transacción.  
  
 La clase <xref:System.ServiceModel.CallbackBehaviorAttribute> se debe aplicar a la clase que implementa el contrato de devolución de llamada. Si se aplica a una implementación de contrato de no dúplex, se produce una excepción <xref:System.InvalidOperationException> en tiempo de ejecución. El ejemplo de código siguiente muestra una clase <xref:System.ServiceModel.CallbackBehaviorAttribute> en un objeto de devolución de llamada que usa el objeto <xref:System.Threading.SynchronizationContext> para determinar el subproceso para serializar las referencias, la propiedad <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> para exigir la validación del mensaje y la propiedad <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> para devolver las excepciones como objetos <xref:System.ServiceModel.FaultException> al servicio para los propósitos de depuración.  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a>Utilizar CallbackDebugBehavior para habilitar el flujo de información de excepción administrada  

 Puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente de nuevo al servicio para fines de depuración estableciendo la propiedad <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> en `true` mediante programación o desde un archivo de configuración de la aplicación.  
  
 Devolver la información de excepción administrada a los servicios puede suponer un riesgo para la seguridad porque los datos de la excepción exponen información sobre la implementación del cliente interna que los servicios desautorizados podrían utilizar. Además, aunque también se pueden establecer las propiedades <xref:System.ServiceModel.Description.CallbackDebugBehavior> mediante programación, puede ser fácil olvidarse de deshabilitar <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> en la implementación.  
  
 Debido a los problemas de seguridad implicados, se recomienda encarecidamente que:  
  
- Utilice un archivo de configuración de la aplicación para establecer el valor de la propiedad <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> en `true`.  
  
- lo haga solamente en escenarios de depuración controlados.  
  
 En el ejemplo de código siguiente se muestra un archivo de configuración de cliente que indica a WCF que devuelva la información de excepción administrada de un objeto de devolución de llamada de cliente en los mensajes SOAP.  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  

## <a name="using-the-clientviabehavior-behavior"></a>Utilizar el comportamiento de ClientViaBehavior  

 Puede utilizar el comportamiento <xref:System.ServiceModel.Description.ClientViaBehavior> para especificar el Identificador uniforme de recursos para el cual se debería crear el canal de transporte. Utilice este comportamiento cuando el destino de la red inmediato no es el procesador de impresión previsto del mensaje. Esto habilita conversaciones de varios saltos cuando la aplicación que realiza la llamada no conoce necesariamente el destino último o cuando el encabezado de destino `Via` no es una dirección.  
  
## <a name="see-also"></a>Vea también

- [Especificación del comportamiento en tiempo de ejecución del servicio](specifying-service-run-time-behavior.md)
