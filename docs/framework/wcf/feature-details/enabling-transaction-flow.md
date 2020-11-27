---
title: Habilitar el flujo de transacciones
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], enabling flow
ms.assetid: a03f5041-5049-43f4-897c-e0292d4718f7
ms.openlocfilehash: 206cbecc35c6b517ddfc3b14f4a1d139cf72fc34
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276755"
---
# <a name="enabling-transaction-flow"></a>Habilitar el flujo de transacciones

Windows Communication Foundation (WCF) proporciona opciones muy flexibles para controlar el flujo de la transacción. La configuración del flujo de transacción de un servicio se puede expresar utilizando una combinación de atributos y configuración.  
  
## <a name="transaction-flow-settings"></a>Configuración del flujo de transacción  

 La configuración del flujo de transacción se genera para un extremo de servicio como resultado de la intersección de los tres valores siguientes:  
  
- El atributo <xref:System.ServiceModel.TransactionFlowAttribute> especificado para cada método en el contrato de servicios.  
  
- La propiedad de enlace `TransactionFlow` en el enlace concreto.  
  
- La propiedad de enlace `TransactionFlowProtocol` en el enlace concreto. La propiedad de enlace `TransactionFlowProtocol` le permite elegir entre dos protocolos de transacción diferentes que puede utilizar para el flujo de una transacción. Las siguientes secciones describen brevemente cada uno de ellos.  
  
### <a name="ws-atomictransaction-protocol"></a>Protocolo WS-AtomicTransaction  

 El protocolo WS-AtomicTransaction (WS-AT) es útil para los escenarios cuando se requiere la interoperabilidad con pilas de protocolo de terceros.  
  
### <a name="oletransactions-protocol"></a>Protocolo OleTransactions  

 El protocolo OleTransactions es útil para los escenarios cuando no se requiere la interoperabilidad con pilas de protocolo de terceros, y el implementador de un servicio conoce de antemano que el servicio de protocolo WS-AT está deshabilitado localmente o la topología de red existente no favorece el uso de WS-AT.  
  
 La tabla siguiente muestra los tipos diferentes de flujos de transacción que se pueden generar utilizando estas combinaciones diversas.  
  
|TransactionFlow<br /><br /> binding|Propiedad de enlace TransactionFlow|Protocolo de enlace TransactionFlowProtocol|Tipo de flujo de transacción|  
|---------------------------------|--------------------------------------|----------------------------------------------|------------------------------|  
|Mandatory|true|WS-AT|La transacción debe fluir en el formato WS-AT interoperable.|  
|Mandatory|true|OleTransactions|La transacción debe fluir en el formato OleTransactions de WCF.|  
|Mandatory|false|No aplicable|No es aplicable porque se trata de una configuración no válida.|  
|Permitido|true|WS-AT|La transacción puede fluir en el formato WS-AT interoperable.|  
|Permitido|true|OleTransactions|La transacción puede fluir en el formato OleTransactions de WCF.|  
|Permitido|false|Cualquier valor|No fluye una transacción.|  
|No permitidos|Cualquier valor|Cualquier valor|No fluye una transacción.|  
  
 La tabla siguiente resume el resultado del procesamiento de mensajes.  
  
|Mensaje entrante|Valor TransactionFlow|Encabezado de transacción|Resultado del procesamiento de mensajes|  
|----------------------|-----------------------------|------------------------|-------------------------------|  
|La transacción coincide con el formato de protocolo esperado|Permitido u obligatorio|`MustUnderstand` es igual que `true`.|Proceso|  
|La transacción no coincide con el formato de protocolo esperado|Mandatory|`MustUnderstand` es igual que `false`.|Rechazado porque se requiere una transacción|  
|La transacción no coincide con el formato de protocolo esperado|Permitido|`MustUnderstand` es igual que `false`.|Rechazado porque no se entiende el encabezado|  
|Transacción que utiliza cualquier formato de protocolo|No permitidos|`MustUnderstand` es igual que `false`.|Rechazado porque no se entiende el encabezado|  
|Sin transacción|Mandatory|N/D|Rechazado porque se requiere una transacción|  
|Sin transacción|Permitido|N/D|Proceso|  
|Sin transacción|No permitidos|N/D|Proceso|  
  
 Mientras cada método en un contrato puede tener requisitos de flujo de transacción diferentes, el valor del protocolo del flujo de transacción se sitúa en el nivel del enlace. Esto significa que todos los métodos que comparten el mismo extremo (y por consiguiente el mismo enlace) también comparten la misma directiva permitiendo o requiriendo el flujo de transacción, así como el mismo protocolo de transacción si es aplicable.  
  
## <a name="enabling-transaction-flow-at-the-method-level"></a>Habilitar el flujo de transacción en el nivel de método  

 Los requisitos de flujo de transacción no son siempre los mismos para todos los métodos en un contrato de servicios. Por lo tanto, WCF también proporciona un mecanismo basado en atributos para permitir expresar las preferencias de flujo de transacción de cada método. <xref:System.ServiceModel.TransactionFlowAttribute> que especifica el nivel en el que una operación del servicio acepta un encabezado de transacción logra esto. Debería marcar sus métodos de contrato de servicios con este atributo si desea habilitar el flujo de la transacción. Este atributo toma uno de los valores de la enumeración <xref:System.ServiceModel.TransactionFlowOption>, en la que el valor predeterminado es <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>. Si se especifica cualquier valor excepto <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>, el método no debe ser unidireccional. Un programador puede utilizar este atributo para especificar requisitos de flujo de transacción del nivel de método o restricciones en tiempo de diseño.  
  
## <a name="enabling-transaction-flow-at-the-endpoint-level"></a>Habilitar el flujo de transacción en el nivel del extremo  

 Además de la configuración del flujo de transacciones del nivel de método que <xref:System.ServiceModel.TransactionFlowAttribute> proporciona el atributo, WCF proporciona una configuración de todo el extremo para que el flujo de la transacción permita a los administradores controlar el flujo de la transacción en un nivel superior.  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>, que le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo logra, así como especificar el formato del protocolo de transacción para las transacciones entrantes.  
  
 Si el enlace ha deshabilitado el flujo de la transacción, pero una de las operaciones en un contrato de servicios requiere una transacción entrante, se produce una excepción de validación en el inicio del servicio.  
  
 La mayoría de los enlaces permanentes que proporciona WCF contienen `transactionFlow` los `transactionProtocol` atributos y para permitirle configurar el enlace específico para aceptar las transacciones entrantes. Para obtener más información acerca de cómo establecer los elementos de configuración, vea [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .  
  
 Un administrador o implementador puede utilizar el flujo de la transacción en el nivel del punto de conexión para configurar los requisitos del flujo de transacción o las restricciones en tiempo de implementación utilizando el archivo de configuración.  
  
## <a name="security"></a>Seguridad  

 Para garantizar la seguridad e integridad del sistema, debe proteger los intercambios de mensajes cuando haya flujo de transacciones entre las aplicaciones. No debería fluir o divulgar los detalles de la transacción a ninguna aplicación que no esté autorizada a participar en la misma transacción.  
  
 Al generar clientes WCF en servicios web desconocidos o que no son de confianza mediante el uso de intercambio de metadatos, las llamadas a operaciones en estos servicios web deben suprimir la transacción actual si es posible. En el ejemplo siguiente se muestra cómo hacerlo:  
  
```csharp
//client code which has an ambient transaction  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Suppress))  
{  
    // No transaction will flow to this operation  
    untrustedProxy.Operation1(...);  
    scope.Complete();  
}  
//remainder of client code  
```  
  
 Además, los servicios se deberían configurar para aceptar las transacciones entrantes solo de los clientes que han autenticado y han autorizado. Solo se deberían aceptar las transacciones entrantes si proceden de clientes de mucha confianza.  
  
## <a name="policy-assertions"></a>Aserciones de directiva  

 WCF usa las aserciones de directiva para controlar el flujo de la transacción. Las aserciones de directiva se pueden encontrar en el documento de directiva de un servicio, que se genera agregando contratos, configuración y atributos. El cliente puede obtener el documento de directiva del servicio mediante un HTTP GET o una solicitud-respuesta de WS-MetadataExchange. Los clientes pueden procesar a continuación el documento de directiva para determinar qué operaciones en un contrato de servicios pueden admitir o cuáles requieren flujo de la transacción.  
  
 Las aserciones de directiva de flujo de transacción afectan al flujo de la transacción especificando los encabezados SOAP que un cliente debería enviar a un servicio para representar una transacción. Todos los encabezados de transacción se deben marcar con `MustUnderstand` igual que `true`. Cualquier mensaje con un encabezado marcado de otro modo se rechaza con un error SOAP.  
  
 Solo una aserción de directiva relacionada con transacción puede estar presente en una operación única. Los documentos de directiva con más de una aserción de transacción en una operación se consideran no válidos y son rechazados por WCF. Además, solo un protocolo de transacción único puede estar presente dentro de cada tipo de puerto. Los documentos de directiva con operaciones que hacen referencia a más de un protocolo de transacción dentro de un solo tipo de puerto se consideran no válidos y son rechazados por la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Los documentos de directiva con aserciones de la transacción presentes en mensajes de salida o mensajes de entrada unidireccionales también se consideran no válidos.
