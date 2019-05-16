---
title: Información general de servicios de flujo de trabajo - WCF
ms.date: 03/30/2017
ms.assetid: e536dda3-e286-441e-99a7-49ddc004b646
ms.openlocfilehash: 757a55363a8cb92fc547750183d1261f51f8f682
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639240"
---
# <a name="workflow-services-overview"></a>Información general de servicios de flujo de trabajo

Servicios de flujo de trabajo son servicios basados en WCF que se implementan mediante flujos de trabajo. Servicios de flujo de trabajo son flujos de trabajo que utilizan las actividades de mensajería para enviar y recibir mensajes de Windows Communication Foundation (WCF). .NET Framework 4.5 presenta varias actividades de mensajería que permiten enviar y recibir mensajes dentro de un flujo de trabajo. Para obtener más información sobre la mensajería de actividades y cómo se puede usar para implementar patrones de intercambio de mensajes diferentes, consulte [actividades de mensajería](messaging-activities.md).

## <a name="benefits-of-using-workflow-services"></a>Ventajas del uso de servicios de flujo de trabajo

Cuando las aplicaciones están cada vez más distribuidas, los servicios individuales se convierten en los responsables de llamar a otros servicios para descargar parte del trabajo. La implementación de estas llamadas como operaciones asincrónicas crea cierta complejidad en el código. El control de errores agrega complejidad, ya que hay que administrar excepciones y proporcionar información de seguimiento detallada. Algunos servicios suelen ejecutarse durante mucho tiempo y pueden ocupar valiosos recursos del sistema mientras esperan recibir información. Debido a estos problemas, las aplicaciones distribuidas suelen ser muy complejas y difíciles de escribir y mantener. Los flujos de trabajo son una manera natural de expresar la coordinación del trabajo asincrónico, sobre todo las llamadas a servicios externos. Los flujos de trabajo también son eficaces para representar procesos de negocio de ejecución prolongada. Son estas calidades las que convierten el flujo de trabajo en un gran recurso para compilar servicios en un entorno distribuido.

## <a name="implementing-a-workflow-service"></a>Implementación de un servicio de flujo de trabajo

Al implementar un servicio WCF, defina varios contratos que describan el servicio y los datos que envía y recibe. Los datos se representan como contratos de datos y contratos de mensajes. WCF y los servicios de flujo de trabajo usan definiciones de contratos de datos y de mensajes como parte de las descripciones del servicio. El servicio expone metadatos (con formato de WSDL) para describir las operaciones del servicio. En WCF, los contratos de servicios y los contratos de operaciones definen el servicio y las operaciones admitidos. Sin embargo, en un servicio de flujo de trabajo, estos contratos forman parte del propio proceso de negocio. Se exponen en metadatos mediante un proceso llamado inferencia del contrato. Cuando un servicio de flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se examina la definición de flujo de trabajo y se genera un contrato en función del conjunto de actividades de mensajería presentes en el flujo de trabajo. En especial, se emplean las siguientes actividades y propiedades para generar el contrato:

Actividad <xref:System.ServiceModel.Activities.Receive>

- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>

- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>

- <xref:System.ServiceModel.Activities.Receive.Action%2A>

Actividad <xref:System.ServiceModel.Activities.SendReply>

- <xref:System.ServiceModel.Activities.SendReply.Action%2A>

Actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope>

El resultado final de inferencia del contrato es una descripción del servicio mediante las mismas estructuras de datos como servicios WCF y los contratos de operación. A continuación, esta información se utiliza para exponer WSDL para el servicio de flujo de trabajo.

> [!NOTE]
> [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] no le permite escribir servicios de flujo de trabajo mediante una definición de contrato existente sin soporte de herramientas adicional. El proceso de inferencia del contrato descrito previamente crea los contratos de servicios de flujo de trabajo. Sin embargo, los contratos de mensajes y los contratos de datos poseen un soporte completo.

## <a name="workflow-services-and-msmq-based-bindings"></a>Servicios de flujo de trabajo y enlaces basados en MSMQ

WCF define dos enlaces basados en MSMQ: <xref:System.ServiceModel.NetMsmqBinding> y <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  Los enlaces basados en MSMQ se utilizan a menudo con servicios de flujo de trabajo debido a la naturaleza de ejecución prolongada de dichos servicios. Los enlaces basados en MSMQ tienen una propiedad `ValidityDuration` que especifica qué longitud pueden tener los mensajes de MSMQ para considerarse válidos. Debido a la naturaleza de ejecución prolongada de los servicios de flujo de trabajo, es posible que la duración de validez de un mensaje de MSMQ pueda finalizar antes de que el servicio de flujo de trabajo pueda procesarlo. Por lo tanto, es muy importante establecer la duración de validez de un enlace de MSMQ a un valor adecuado. Este valor se debe elegirse dependiendo del flujo de trabajo y de cómo procesa los mensajes. Por ejemplo, si tiene un flujo de trabajo con una actividad <xref:System.ServiceModel.Activities.Receive> seguido de una actividad personalizada que tarda 10 minutos en ejecutarse y seguido de otra actividad <xref:System.ServiceModel.Activities.Receive>, el valor correcto de `ValidityDuration` sería superior a 10 minutos.

## <a name="hosting-a-workflow-service"></a>Hospedar un servicio de flujo de trabajo

Como los servicios WCF, se deben hospedar servicios de flujo de trabajo. Servicios de WCF usan el <xref:System.ServiceModel.ServiceHost> clase para hospedar los servicios y flujo de trabajo de los servicios usan <xref:System.ServiceModel.Activities.WorkflowServiceHost> para hospedar los servicios. Como los servicios WCF, flujo de trabajo servicios se pueden hospedar en una variedad de formas, por ejemplo:

- En una aplicación administrada de .NET Framework.

- En Internet Information Services (IIS).

- En el Servicio de activación de procesos de Windows (WAS).

- En un servicio Windows administrado.

Servicios de flujo de trabajo hospedados en una aplicación administrada de .NET Framework o crear una instancia de un servicio de Windows administrado la <xref:System.ServiceModel.Activities.WorkflowServiceHost> clase y pasarle una instancia de la <xref:System.ServiceModel.Activities.WorkflowService> que contiene la definición de flujo de trabajo dentro de la <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> propiedad. Una definición de flujo de trabajo que contiene actividades de mensajería se expone como un servicio de flujo de trabajo.

Para hospedar un servicio de flujo de trabajo en IIS o WAS, coloque el archivo .xamlx que contiene la definición del servicio de flujo de trabajo en un directorio virtual. Un punto de conexión predeterminado (mediante <xref:System.ServiceModel.BasicHttpBinding>) es creado automáticamente para obtener más información, consulte [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md). También puede colocar un archivo Web.config en el directorio virtual para especificar sus propios puntos de conexión. Si la definición de flujo de trabajo es en un ensamblado, puede colocar un archivo .svc en el directorio virtual y el ensamblado de flujo de trabajo en el directorio App_Code. El archivo .svc debe especificar el generador de host de servicio y la clase que implementa el servicio de flujo de trabajo. En el siguiente ejemplo, se indica cómo especificar el generador de host de servicio y especificar la clase que implementa el servicio de flujo de trabajo.

```
<%@ServiceHost Factory=" System.ServiceModel.Activities.Activation.WorkflowServiceHostFactory
Service="EchoService"%>
```
