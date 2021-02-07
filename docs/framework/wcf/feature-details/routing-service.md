---
description: 'Más información acerca de: servicio de enrutamiento'
title: Servicio de enrutamiento
ms.date: 03/30/2017
ms.assetid: ca7c216a-5141-4132-8193-102c181d2eba
ms.openlocfilehash: 29fec780e6bc9266a8fe17d779ff0998e13e5c68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733260"
---
# <a name="routing-service"></a>Servicio de enrutamiento

El Servicio de enrutamiento es un intermediario SOAP genérico que actúa como un enrutador de mensajes. La funcionalidad principal del servicio de enrutamiento es la capacidad de enrutar mensajes según su contenido, lo que permite reenviar un mensaje a un punto de conexión de cliente en función de un valor dentro del propio mensaje, en el encabezado o el cuerpo del mensaje.

<xref:System.ServiceModel.Routing.RoutingService>Se implementa como un servicio de Windows Communication Foundation (WCF) en el <xref:System.ServiceModel.Routing> espacio de nombres. El servicio de enrutamiento expone uno o más extremos de servicio que reciben mensajes y, a continuación, enruta cada mensaje a uno o más extremos de cliente en función del contenido del mensaje. El servicio proporciona las siguientes características:

- Enrutamiento basado en contenido

  - Agregación de servicios

  - Control de versiones de servicios

  - Enrutamiento por prioridad

  - Configuración dinámica

- Puente protocolar

- Procesamiento SOAP

- Control de errores avanzado

- puntos de conexión de reserva

Aunque es posible crear un servicio intermedio que logre uno o más de estos objetivos, a menudo este tipo de implementación está vinculado a una solución o un escenario concretos y no se puede aplicar directamente a las nuevas aplicaciones.

El servicio de enrutamiento proporciona un intermediario de SOAP genérico, dinámicamente configurable y conectable que es compatible con los modelos de canal y de servicio de WCF y permite realizar el enrutamiento basado en contenido de mensajes basados en SOAP.

> [!NOTE]
> Actualmente, el servicio de enrutamiento no permite enrutar servicios de WCF REST.  Para enrutar las llamadas de REST, considere la posibilidad de usar <xref:System.Web.Routing> o el [enrutamiento de solicitud de aplicación](https://go.microsoft.com/fwlink/?LinkId=164589).

## <a name="content-based-routing"></a>Enrutamiento basado en contenido

El enrutamiento basado en contenido es la capacidad de enrutar un mensaje en función de uno o más valores contenidos dentro del mensaje. El servicio de enrutamiento inspecciona cada mensaje y lo enruta al punto de conexión de destino en función del contenido del mensaje y de la lógica de enrutamiento creada. El enrutamiento basado en contenido proporciona una base para la agregación de servicios, el control de versiones del servicio y el enrutamiento de prioridad.

Para implementar el enrutamiento basado en contenido, el servicio de enrutamiento se basa en las implementaciones <xref:System.ServiceModel.Dispatcher.MessageFilter> que se utilizan para coincidir con valores concretos dentro de los mensajes que se van a enrutar. Si un **MessageFilter** coincide con un mensaje, el mensaje se enruta al extremo de destino asociado con **MessageFilter**.  Los filtros de mensajes se agrupan juntos en tablas de filtros (<xref:System.ServiceModel.Routing.Configuration.FilterTableCollection>) para construir una lógica de enrutamiento compleja. Por ejemplo, una tabla de filtros podría contener cinco filtros de mensajes excluyentes entre sí que hagan que los mensajes se enruten a solo uno de los cinco puntos de conexión de destino.

El servicio de enrutamiento le permite configurar la lógica usada para realizar enrutamientos basados en contenido, así como actualizar dinámicamente la lógica del enrutamiento en tiempo de ejecución.

A través de la agrupación de filtros de mensajes en tablas de filtros, puede crearse una lógica de enrutamiento que le permita administrar varios escenarios de enrutamiento, como:

- Agregación de servicios

- Control de versiones de servicios

- Enrutamiento por prioridad

- Configuración dinámica

Para obtener más información acerca de los filtros de mensajes y las tablas de filtros, vea [Introducción a enrutamiento](routing-introduction.md) y [filtros de mensajes](message-filters.md).

### <a name="service-aggregation"></a>Agregación de servicios

Mediante el enrutamiento basado en contenido, puede exponer un punto de conexión que recibe los mensajes de las aplicaciones cliente externas y, a continuación, enruta cada mensaje al punto de conexión interno adecuado en función de un valor del mensaje. Esto es útil para proporcionar un punto de conexión concreto para diversas aplicaciones back-end y también presentar un punto de conexión de la aplicación a los clientes mientras factoriza su aplicación en diversos servicios.

### <a name="service-versioning"></a>Control de versiones del servicio

Cuando migra a una nueva versión de la solución, puede que tenga que mantener la versión antigua en paralelo para servir a los clientes existentes. A menudo, esto requiere que los clientes que se conectan a la versión más reciente usen una dirección diferente al comunicarse con la solución. El servicio de enrutamiento le permite exponer un punto de conexión de servicio que sirve a ambas versiones de la solución enrutando los mensajes a la solución adecuada en función de la información específica de la versión contenida en el mensaje. Para obtener un ejemplo de este tipo de implementación, vea [Cómo: control de versiones del servicio](how-to-service-versioning.md).

### <a name="priority-routing"></a>Enrutamiento de prioridad

Al proporcionar un servicio para varios clientes, puede tener un contrato de nivel de servicio con algunos socios que requiere que todos los datos de estos socios se procesen por separado de los de otros clientes. Mediante un filtro que busca la información específica del cliente incluida en el mensaje, puede enrutar con facilidad los mensajes de socios concretos a un punto de conexión creado para cumplir los requisitos de su contrato de nivel de servicio.

## <a name="dynamic-configuration"></a>Configuración dinámica

Para admitir sistemas vitales para una misión, donde los mensajes se deben procesar sin ninguna interrupción del servicio, es vital que pueda modificar la configuración de componentes dentro del sistema durante el tiempo de ejecución. Para permitir esta necesidad, el servicio de enrutamiento proporciona una implementación <xref:System.ServiceModel.IExtension%601>, <xref:System.ServiceModel.Routing.RoutingExtension>, que permite realizar una actualización dinámica de la configuración del servicio de enrutamiento durante el tiempo de ejecución.

Para obtener más información acerca de la configuración dinámica del servicio de enrutamiento, consulte [Introducción al enrutamiento](routing-introduction.md).

## <a name="protocol-bridging"></a>Puente protocolar

Uno de los desafíos en escenarios intermedios es que los extremos internos pueden tener distintos requisitos de versión de SOAP o transporte que el extremo en el que se reciben los mensajes. Para admitir este escenario, el servicio de enrutamiento puede acortar los protocolos, incluido el procesamiento del mensaje de SOAP a <xref:System.ServiceModel.Channels.MessageVersion> requerido por los extremos de destino. De esta manera, se puede usar un protocolo para la comunicación interna, mientras que el otro se usa para la comunicación externa.

Para admitir el enrutamiento de mensajes entre extremos con transportes diferentes, el servicio de enrutamiento usa enlaces proporcionados por el sistema que permiten al servicio acortar los protocolos que no sean iguales. Esto se produce automáticamente cuando el punto de conexión de servicio expuesto por el servicio de enrutamiento usa un protocolo diferente que el de los puntos de conexión de cliente a los que se enrutan los mensajes.

## <a name="soap-processing"></a>Procesamiento de SOAP

Un requisito de enrutamiento común es la capacidad de enrutar mensajes entre extremos con diferentes requisitos de SOAP. Para admitir este requisito, el servicio de enrutamiento proporciona un <xref:System.ServiceModel.Routing.SoapProcessingBehavior> que crea automáticamente un nuevo **MessageVersion** que cumple los requisitos del punto de conexión de destino antes de que el mensaje se enrute a él. Este comportamiento también crea un nuevo **MessageVersion** para cualquier mensaje de respuesta antes de devolverlo a la aplicación cliente que lo solicita, para asegurarse de que el **MessageVersion** de la respuesta coincide con el de la solicitud original.

Para obtener más información sobre el procesamiento SOAP, vea [Introducción al enrutamiento](routing-introduction.md).

## <a name="error-handling"></a>Tratamiento de errores

En un sistema compuesto de servicios distribuidos que confían en las comunicaciones por red, es importante asegurarse de que las comunicaciones dentro del sistema son resistentes a los errores de red transitorios.  El servicio de enrutamiento implementa un control de errores que le permite administrar muchos casos de fallos de comunicación que, de otro modo, podrían producir una interrupción del suministro del servicio.

Si el servicio de enrutamiento encuentra una clase <xref:System.ServiceModel.CommunicationException> mientras intenta enviar un mensaje, se activará el control de errores.  Estas excepciones indican normalmente que se encontró un problema al intentar establecer comunicación con el extremo de cliente definido, como <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>.  El código de control de errores también detectará e intentará volver a realizar el envío cuando se produzca un **TimeoutException** , que es otra excepción común que no se deriva de **CommunicationException**.

Para obtener más información sobre el control de errores, consulte [Introducción al enrutamiento](routing-introduction.md).

## <a name="backup-endpoints"></a>puntos de conexión de reserva

Además de los extremos de cliente de destino asociados a cada definición de filtro en la tabla de filtros, también puede crear una lista de extremos de reserva a los que se enrutará el mensaje en caso de que se produzca un error de la transmisión. Si se produce un error y se define una lista de reserva para la entrada del filtro, el servicio de enrutamiento intentará enviar el mensaje al primer extremo definido en la lista. Si este intento de transmisión no se realiza correctamente, el servicio probará el punto de conexión siguiente, y continuará con este proceso hasta que el intento de transmisión sea correcto, devuelva un error no relacionado con la transmisión o todos los puntos de conexión de la lista de reserva hayan devuelto un error de la transmisión.

Para obtener más información acerca de los puntos de conexión de reserva, vea [Introducción a enrutamiento](routing-introduction.md) y [filtros de mensajes](message-filters.md).

## <a name="streaming"></a>Streaming

El servicio de enrutamiento puede transmitir los mensajes correctamente si establece el enlace para que admita la transmisión por secuencias.  Sin embargo, hay algunas condiciones en las que es necesario poner en el búfer los mensajes:

- Multidifusión (usa el búfer para crear copias adicionales de los mensajes)

- Conmutación por error (usa el búfer en el caso de que sea necesario enviar el mensaje a una reserva)

- System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly es false (usa el búfer para presentar MessageFilterTable con un MessageBuffer de modo que los filtros pueden inspeccionar el cuerpo)

- Configuración dinámica

## <a name="see-also"></a>Vea también

- [Introducción al enrutamiento](routing-introduction.md)
- [Enrutar contratos](routing-contracts.md)
- [Filtros de mensajes](message-filters.md)
