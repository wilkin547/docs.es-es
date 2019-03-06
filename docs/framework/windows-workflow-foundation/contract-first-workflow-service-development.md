---
title: Desarrollo de servicio de flujo de trabajo de contrato primero
ms.date: 03/30/2017
ms.assetid: e5dbaa7b-005f-4330-848d-58ac4f42f093
ms.openlocfilehash: 3b015b8c58e5ee3acbb1277d00523a85ee96da46
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373067"
---
# <a name="contract-first-workflow-service-development"></a>Desarrollo de servicio de flujo de trabajo de contrato primero
A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], las características de Windows Workflow Foundation (WF) una mejor integración entre los servicios web y flujos de trabajo en forma de desarrollo de flujo de trabajo de contrato primero. La herramienta de desarrollo de flujo de trabajo de contrato primero permite diseñar el contrato en Code First. La herramienta después genera automáticamente una plantilla de actividad en el cuadro de herramientas para las operaciones del contrato. Este tema proporciona información general sobre cómo se asignan las actividades y las propiedades de un servicio de flujo de trabajo a los atributos de un contrato de servicio. Para obtener un ejemplo paso a paso de creación de un servicio de flujo de trabajo de contrato primero, vea [Cómo: Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md).  
  
## <a name="in-this-topic"></a>En este tema  
  
-   [Asignación de atributos de contrato de servicio a los atributos de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MappingAttributes)  
  
    -   [Atributos de contrato de servicio](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
    -   [Atributos de contrato de operación](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
    -   [Atributos de contrato de mensaje](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
    -   [Atributos de contrato de datos](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
    -   [Atributos de contrato de error](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
-   [Información de implementación y soporte técnico adicionales](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#AdditionalSupport)  
  
    -   [Características del contrato de servicio no admitido](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
    -   [Generación de las actividades de mensajes configuradas](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
## <a name="MappingAttributes"></a> Asignación de atributos de contrato de servicio a los atributos de flujo de trabajo  
 En las tablas de las siguientes secciones se especifican los diferentes atributos y propiedades de WCF, así como el modo en que se asignan a las actividades y a las propiedades de mensajería en un flujo de trabajo de contrato primero.  
  
-   [Atributos de contrato de servicio](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
-   [Atributos de contrato de operación](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
-   [Atributos de contrato de mensaje](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
-   [Atributos de contrato de datos](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
-   [Atributos de contrato de error](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
### <a name="ServiceContract"></a> Atributos de contrato de servicio  
  
|Nombre de la propiedad|Compatible|Descripción|Validación WF|  
|-------------------|---------------|-----------------|-------------------|  
|CallbackContract|No|Obtiene o establece el tipo de contrato de devolución de llamada cuando el contrato es un contrato dúplex.|(No disponible)|  
|ConfigurationName|No|Obtiene o establece el nombre utilizado para buscar el servicio en un archivo de configuración de la aplicación.|(No disponible)|  
|HasProtectionLevel|Sí|Obtiene un valor que indica si el miembro tiene un nivel de protección asignado.|Receive.ProtectionLevel no debe ser NULL.|  
|Name|Sí|Obtiene o establece el nombre para el \<portType > elemento de lenguaje de descripción de servicios Web (WSDL).|Receive.ServiceContractName.LocalName debe coincidir.|  
|Espacio de nombres|Sí|Obtiene o establece el espacio de nombres de los \<portType > elemento de lenguaje de descripción de servicios Web (WSDL).|Receive.ServiceContractName.NameSpace debe coincidir.|  
|ProtectionLevel|Sí|Especifica si el enlace para el contrato debe admitir el valor de la propiedad ProtectionLevel.|Receive.ProtectionLevel debe coincidir.|  
|SessionMode|No|Obtiene o establece si se permiten sesiones, si no se permiten o si son necesarias.|(No disponible)|  
|TypeId|No|Cuando se implementa en una clase derivada, solo recibe un identificador para este atributo. (Heredado del atributo)|(No disponible)|  
  
 Inserte aquí el cuerpo de la subsección.  
  
### <a name="OperationContract"></a> Atributos de contrato de operación  
  
|Nombre de la propiedad|Compatible|Descripción|Validación WF|  
|-------------------|---------------|-----------------|-------------------|  
|Acción|Sí|Obtiene o establece la acción WS-Addressing del mensaje de solicitud.|Receive.Action debe coincidir.|  
|AsyncPattern|No|Indica que una operación se implementa de forma asincrónica utilizando un inicio\<methodName > y End\<methodName > par de métodos en un contrato de servicio.|(No disponible)|  
|HasProtectionLevel|Sí|Obtiene un valor que indica si los mensajes para esta operación deben cifrarse, firmarse o ambos.|Receive.ProtectionLevel no debe ser NULL.|  
|IsInitiating|No|Obtiene o establece un valor que indica si el método implementa una operación que puede iniciar una sesión en el servidor (si tal sesión existe).|(No disponible)|  
|IsOneWay|Sí|Obtiene o establece un valor que indica si una operación devuelve un mensaje de respuesta.|(Ningún SendReply para este Receive o ningún ReceiveReply para este envío).|  
|IsTerminating|No|Obtiene o establece un valor que indica si la operación de servicio hace que el servidor cierre la sesión después de enviar el mensaje de respuesta, si lo hubiera.|(No disponible)|  
|Name|Sí|Obtiene o establece el nombre de la operación.|Receive.OperationName debe coincidir.|  
|ProtectionLevel|Sí|Obtiene o establece un valor que especifica si los mensajes de una operación deben cifrarse, firmarse o ambos.|Receive.ProtectionLevel debe coincidir.|  
|ReplyAction|Sí|Obtiene o establece el valor de la acción SOAP para el mensaje de respuesta de la operación.|SendReply.Action debe coincidir.|  
|TypeId|No|Cuando se implementa en una clase derivada, solo recibe un identificador para este atributo. (Heredado del atributo)|(No disponible)|  
  
### <a name="MessageContract"></a> Atributos de contrato de mensaje  
  
|Nombre de la propiedad|Compatible|Descripción|Validación WF|  
|-------------------|---------------|-----------------|-------------------|  
|HasProtectionLevel|Sí|Obtiene un valor que indica si el mensaje tiene un nivel de protección.|Ninguna validación (Receive.Content y SendReply.Content deben coincidir con el tipo de contrato de mensaje).|  
|IsWrapped|Sí|Obtiene o establece un valor que especifica si el cuerpo del mensaje tiene un elemento contenedor.|Ninguna validación (Receive.Content y Sendreply.Content deben coincidir con el tipo de contrato de mensaje).|  
|ProtectionLevel|No|Obtiene o establece un valor que especifica si los mensajes deben cifrarse, firmarse o las dos cosas.|(No disponible)|  
|TypeId|Sí|Cuando se implementa en una clase derivada, solo recibe un identificador para este atributo. (Heredado del atributo)|Ninguna validación (Receive.Content y SendReply.Content deben coincidir con el tipo de contrato de mensaje).|  
|WrapperName|Sí|Obtiene o establece el nombre del elemento contenedor del cuerpo del mensaje.|Ninguna validación (Receive.Content y SendReply.Content deben coincidir con el tipo de contrato de mensaje).|  
|WrapperNamespace|No|Obtiene o establece el espacio de nombres del elemento contenedor del cuerpo del mensaje.|(No disponible)|  
  
### <a name="DataContract"></a> Atributos de contrato de datos  
  
|Nombre de la propiedad|Compatible|Descripción|Validación WF|  
|-------------------|---------------|-----------------|-------------------|  
|IsReference|No|Obtiene o establece un valor que indica si conservar los datos de referencia al objeto.|(No disponible)|  
|Name|Sí|Obtiene o establece el nombre del contrato de datos para el tipo.|Ninguna validación (Receive.Content y SendReply.Content deben coincidir con el tipo de contrato de mensaje).|  
|Espacio de nombres|Sí|Obtiene o establece el espacio de nombres del contrato de datos para el tipo.|Ninguna validación (Receive.Content y SendReply.Content deben coincidir con el tipo de contrato de mensaje).|  
|TypeId|No|Cuando se implementa en una clase derivada, solo recibe un identificador para este atributo. (Heredado del atributo)|(No disponible)|  
  
### <a name="FaultContract"></a> Atributos de contrato de error  
  
|Nombre de la propiedad|Compatible|Descripción|Validación WF|  
|-------------------|---------------|-----------------|-------------------|  
|Acción|Sí|Obtiene o establece la acción del mensaje de error de SOAP que se especifica como parte del contrato de la operación.|SendReply.Action debe coincidir.|  
|DetailType|Sí|Obtiene el tipo de un objeto serializable que contiene información de error.|SendReply.Content debe coincidir con el tipo|  
|HasProtectionLevel|No|Obtiene un valor que indica si el mensaje de error de SOAP tiene un nivel de protección asignado.|(No disponible)|  
|Name|No|Obtiene o establece el nombre del mensaje de error en el Lenguaje de descripción de servicios Web (WSDL).|(No disponible)|  
|Espacio de nombres|No|Obtiene o establece el espacio de nombres del error de SOAP.|(No disponible)|  
|ProtectionLevel|No|Especifica el nivel de protección que el error de SOAP requiere del enlace.|(No disponible)|  
|TypeId|No|Cuando se implementa en una clase derivada, solo recibe un identificador para este atributo. (Heredado del atributo)|(No disponible)|  
  
## <a name="AdditionalSupport"></a> Información de implementación y soporte técnico adicionales  
  
-   [Características del contrato de servicio no admitido](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
-   [Generación de las actividades de mensajes configuradas](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
### <a name="UnsupportedFeatures"></a> Características del contrato de servicio no admitido  
  
-   No se admite el uso de tareas TPL (biblioteca de tareas en paralelo) en contratos.  
  
-   No se admite la herencia en contratos de servicio.  
  
### <a name="ActivityGeneration"></a> Generación de las actividades de mensajes configuradas  
 Dos métodos static públicos se agregan a las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> para admitir la creación de actividades de mensaje preconfiguradas al usar servicios de flujo de trabajo de contrato primero.  
  
-   <xref:System.ServiceModel.Activities.Receive.FromOperationDescription%2A?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Activities.SendReply.FromOperationDescription%2A?displayProperty=nameWithType>  
  
 La actividad generada por estos métodos debe pasar la validación del contrato y, por consiguiente, estos métodos se usan internamente como parte de la lógica de validación para <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>. 
  <xref:System.ServiceModel.Activities.Receive.OperationName%2A>, <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>, <xref:System.ServiceModel.Activities.Receive.Action%2A>, <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>, <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> y <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> están preconfigurados para coincidir con el contrato importado. En la página de propiedades de contenido para las actividades en el Diseñador de flujo de trabajo, el **mensaje** o **parámetros** secciones también están preconfiguradas para coincidir con el contrato.  
  
 Error de WCF contratos también se controlan mediante la devolución de un conjunto independiente de configurado <xref:System.ServiceModel.Activities.SendReply> actividades para cada uno de los errores que se muestran en el <xref:System.ServiceModel.Description.OperationDescription.Faults%2A> <xref:System.ServiceModel.Description.FaultDescriptionCollection>.  
  
 Para otras partes de <xref:System.ServiceModel.Description.OperationDescription> que no están admitidas por los servicios WF hoy en día (por ejemplo, los comportamientos de WebGet/WebInvoke o comportamientos de operación personalizado), la API omitirá estos valores como parte de la generación y la configuración. No se producirán excepciones.
