---
description: 'Más información acerca de: atributos de transacción de ServiceModel'
title: Atributos de transacción de ServiceModel
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel attributes
ms.assetid: 1e0d2436-6ae5-439b-9765-a448d6f60000
ms.openlocfilehash: 0b443fc6b9503007574608afe03c5e0508f666d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793485"
---
# <a name="servicemodel-transaction-attributes"></a>Atributos de transacción de ServiceModel

Windows Communication Foundation (WCF) proporciona propiedades de tres <xref:System.ServiceModel> atributos estándar que permiten configurar el comportamiento de las transacciones para un servicio WCF:

- <xref:System.ServiceModel.TransactionFlowAttribute>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>

- <xref:System.ServiceModel.OperationBehaviorAttribute>

## <a name="transactionflowattribute"></a>TransactionFlowAttribute

El atributo <xref:System.ServiceModel.TransactionFlowAttribute> especifica la predisposición de una operación en un contrato de servicio para aceptar las transacciones entrantes de un cliente. El atributo proporciona la propiedad siguiente a este control: las transacciones utilizan la enumeración <xref:System.ServiceModel.TransactionFlowOption> para especificar si una transacción entrante es <xref:System.ServiceModel.TransactionFlowOption.Mandatory>, <xref:System.ServiceModel.TransactionFlowOption.Allowed>o <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.

Éste es el único atributo que relaciona las operaciones de servicio con las interacciones externas con un cliente. Los atributos descritos en las siguientes secciones se relacionan con el uso de transacciones dentro de la ejecución de la operación.

## <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute

El atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> especifica el comportamiento de ejecución interno de una implementación de contrato de servicio. Entre las propiedades específicas de transacciones de este atributo se incluyen:

- <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionAutoCompleteOnSessionClose%2A> especifica si completar una transacción incompleta cuando la sesión se cierra. El valor predeterminado de esta propiedad es `false`. Si esta propiedad es `true`, y la sesión entrante se cerró correctamente en lugar de cerrarse debido a errores de red o de cliente, se completa correctamente cualquier transacción incompleta. De lo contrario, si esta propiedad es `false` o si no se cerró la sesión correctamente, se deshace cualquier transacción incompleta cuando se cierra la sesión. Si esta propiedad es `true`, el canal de entrada debe basarse en sesión.

- <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> especifica si se libera la instancia del servicio subyacente cuando se completa una transacción. El valor predeterminado de esta propiedad es `true`. El siguiente mensaje entrante hace que se cree una nueva instancia subyacente, descartando cualquiera estado por transacción que la instancia anterior pudiese haber retenido. Liberar una instancia de servicio es una acción interna que realiza el servicio y no tiene ningún impacto en ninguna conexión ni sesiones existentes que los clientes puedan haber establecido. Esta funcionalidad es equivalente a la característica de activación just-in-time que proporciona COM+. Si la propiedad es `true`, <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> debe ser igual a <xref:System.ServiceModel.ConcurrencyMode.Single>. De lo contrario, el servicio produce una excepción de validación de configuración no válida durante el inicio.

- <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> especifica el nivel de aislamiento que se utilizará para las transacciones dentro del servicio; esta propiedad toma uno de los valores <xref:System.Transactions.IsolationLevel>. Si la propiedad de nivel de aislamiento local no es <xref:System.Transactions.IsolationLevel.Unspecified>, el nivel de aislamiento de una transacción entrante debe coincidir con el valor de esta propiedad local. De lo contrario, se rechaza la transacción entrante y se devuelve un error al cliente. Si <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`, y no se fluye ninguna transacción, esta propiedad determina el valor <xref:System.Transactions.IsolationLevel> que se utilizará para la transacción creada localmente. Si se establece <xref:System.Transactions.IsolationLevel> como <xref:System.Transactions.IsolationLevel.Unspecified>, se usa <xref:System.Transactions.IsolationLevel><xref:System.Transactions.IsolationLevel.Serializable>.

- <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> especifica el período de tiempo dentro del que una nueva transacción creada en el servicio debe completarse. Si se alcanza este período de tiempo y no se ha completado la transacción, se anulará. <xref:System.TimeSpan> se utiliza como tiempo de espera <xref:System.Transactions.TransactionScope> para cualquier operación que tenga <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> destablecida como `true` y para la que se creó una nueva transacción. El tiempo de espera es la duración máxima permitida desde la creación de la transacción hasta la finalización de la fase 1 en el protocolo de confirmación de dos fases. El valor de tiempo de espera utilizado es siempre el valor inferior entre la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> y el valor de configuración `transactionTimeout`.

## <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute

El atributo <xref:System.ServiceModel.OperationBehaviorAttribute> especifica los comportamientos de los métodos en la implementación del servicio. Puede utilizarlo para indicar el comportamiento de ejecución concreto de la operación. Las propiedades de este atributo no afectan a la descripción del lenguaje de descripción de servicios web (WSDL) del contrato de servicio y son meramente elementos del modelo de programación de WCF que permiten características comunes que los desarrolladores tienen que implementar por sí mismos.

Este atributo tiene las siguientes propiedades específicas de transacciones:

- <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> especifica si un método debe ejecutarse dentro de un ámbito de transacciones activo. De manera predeterminada, es `false`. Si el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> no se establece para un método, también implica que el método no se ejecutará en una transacción. Si no se requiere un ámbito de transacciones para una operación, cualquier transacción que esté presente dentro del encabezado del mensaje no se activa y permanece como un elemento de <xref:System.ServiceModel.OperationContext.IncomingMessageProperties%2A> de <xref:System.ServiceModel.OperationContext>. Si se requiere un ámbito de la transacción para una operación, el origen para la transacción se deriva a partir de uno de los siguientes elementos:

  - Si una transacción fluye a partir del cliente, se ejecuta el método bajo un ámbito de transacciones creado mediante esa transacción distribuida.

  - Con un transporte en cola, se usa la transacción utilizada para quitar el mensaje de la cola. Observe que la transacción utilizada no es una transacción de flujo, puesto que no la proporcionó el remitente original del mensaje.

  - Un transporte personalizado puede proporcionar una transacción mediante el uso de `TransportTransactionProperty`.

  - Si nada de lo anterior proporciona un origen externo para una transacción, se crea inmediatamente una nueva instancia <xref:System.Transactions.Transaction> antes de llamar al método.

- <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se produce ninguna excepción no controlada. Si esta propiedad es `true`, la infraestructura de la llamada marca automáticamente la transacción como "completada" si el método de usuario vuelve sin producir una excepción. Si esta propiedad es `false`, la transacción está adjunta a la instancia y solo se marca como "completada" si el cliente llama a un método subsiguiente marcado con esta propiedad igual a `true`, o si un método subsiguiente llama explícitamente a <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>. Error al realizar cualquiera de estos resultados en la transacción, que nunca se completa y no se confirma el trabajo contenido, a menos que la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionAutoCompleteOnSessionClose%2A> esté establecida como `true`. Si esta propiedad se establece como `true`, debe utilizar un canal con una sesión y <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> debe establecerse como <xref:System.ServiceModel.InstanceContextMode.PerSession>.
