---
title: Procedimientos recomendados para lograr sesiones confiables
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 1d9671e7e3124d535b66de8cd8468f76dcb32b10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857992"
---
# <a name="best-practices-for-reliable-sessions"></a>Procedimientos recomendados para lograr sesiones confiables

En este tema se describe los procedimientos recomendados para las sesiones confiables.

## <a name="setting-maxtransferwindowsize"></a>Establecimiento de MaxTransferWindowSize

Las sesiones confiables en Windows Communication Foundation (WCF) utilizan una ventana de transferencia para retener los mensajes en el cliente y el servicio. La propiedad configurable <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica cuántos mensajes puede contener la ventana de transferencia.

En el remitente, esto indica cuántos mensajes puede contener la ventana de transferencia mientras espera las confirmaciones; en el receptor, indica cuántos mensajes almacenar en búfer para el servicio.

Elección del tamaño adecuado afecta a la eficacia de la red y la capacidad óptima del servicio. Las secciones siguientes detallan lo que debe considerar al elegir un valor para esta propiedad y el impacto del valor.

El tamaño de ventana de transferencia predeterminado es ocho mensajes.

### <a name="efficient-use-of-the-network"></a>Uso eficaz de la red

En este contexto, el término *red* corresponde a todo lo que se utiliza como base de la comunicación entre un cliente (remitente) y un servicio (receptor). Esto incluye las conexiones de transporte y cualquier intermediario o puentes entre ellas, incluidos los enrutadores SOAP o proxys HTTP/firewalls.

El uso eficaz de la red garantiza el uso total de la capacidad de la red. La cantidad de datos que se pueden transferir por segundo a través de la red (*velocidad de datos*) y el tiempo necesario para transferir datos desde el remitente al receptor (*latencia*) afectan a la eficacia con la red se utiliza.

En el remitente, la propiedad <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica cuántos mensajes puede contener su ventana de transferencia mientras espera las confirmaciones. Si la latencia de red es alta y con el fin de garantizar un remitente con capacidad de respuesta y un uso eficaz de la red, debe aumentar el tamaño de la ventana de transferencia.

Por ejemplo incluso si el remitente se mantiene al día con velocidad de datos, latencia podría ser alta si existen varios intermediarios entre el remitente y receptor o los datos deben pasar a través de un intermediario con pérdida de datos o la red. Por lo tanto, el remitente tiene que esperar las confirmaciones de los mensajes en su ventana de transferencia antes de aceptar mensajes nuevos que se envían en la conexión. Cuanto menor sea el búfer con una latencia alta, menos efectivos el uso de la red. Por otro lado, demasiado alto un tamaño de la ventana de transferencia puede afectar al servicio porque el servicio puede necesitar ponerse al día para la alta tasa de datos enviados por el cliente.

### <a name="running-the-service-to-capacity"></a>Ejecuta el servicio a la capacidad

Como la red se usa de forma eficaz, lo ideal es que también desea que el servicio para ejecutarse a capacidad óptima. La propiedad de tamaño de la ventana de transferencia en el receptor indica cuántos mensajes puede almacenar en búfer el receptor. Este almacenamiento en búfer de mensajes no solo ayuda al control del flujo de la red, sino también permite al servicio ejecutarse a capacidad completa. Por ejemplo, si el búfer es un mensaje y los mensajes llegan antes de que el servicio pueda procesarlos, a continuación, la red podría colocar mensajes y podría ser sobre- o infrautilizarse la capacidad.

Mediante un búfer aumenta la disponibilidad del servicio tal como lo recibe y almacena en búfer un mensaje al procesar los mensajes recibidos con anterioridad al mismo tiempo.

Se recomienda usar el mismo `MaxTransferWindowSize` en el remitente y receptor.

### <a name="enabling-flow-control"></a>Habilitar control de flujo

*Control de flujo* es un mecanismo que asegura que el remitente y receptor mantengan al día entre sí, es decir, los mensajes son consumidos y actuar tan rápido como el que se producen. El tamaño de la ventana de transferencia en el cliente y el servicio asegura que el remitente y receptor se encuentran dentro de una ventana razonable de sincronización.

Se recomienda encarecidamente que establezca la propiedad <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> a `true` cuando se usa una sesión confiable entre un cliente WCF y un servicio WCF.

## <a name="setting-maxpendingchannels"></a>Establecimiento de MaxPendingChannels

Al escribir un servicio que permite la comunicación de la sesión confiable desde clientes diferentes, es posible tener muchos clientes establezcan una sesión confiable en el servicio al mismo tiempo. La respuesta del servicio en estas situaciones depende de la propiedad `MaxPendingChannels`.

Cuando el remitente crea un canal de sesión confiable en un receptor, un protocolo de enlace entre ellos establece una sesión confiable. Una vez establecida la sesión confiable, el canal se coloca en una cola de canales pendientes para que el servicio los acepte. La propiedad `MaxPendingChannels` indica cuántos canales pueden estar en este estado.

Es posible que el servicio esté en un estado donde no puede aceptar más canales. Si la cola está llena, se rechaza un intento para establecer una sesión confiable y el cliente debe volver a intentarlo.

También es posible que los canales pendientes de la cola permanecen en la cola durante mucho tiempo. Mientras tanto, puede producirse un tiempo de espera de inactividad en la sesión confiable, produciendo que el canal para realizar la transición a un estado de error.

Al escribir un servicio que atiende a varios clientes simultáneamente, debe establecer un valor que es adecuado para sus necesidades. Establecer un valor demasiado alto para el `MaxPendingChannels` propiedad afecta a su espacio de trabajo.

El valor predeterminado de <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> es cuatro canales.

## <a name="reliable-sessions-and-hosting"></a>Hospedaje y sesiones confiables

Cuando web hospedar un servicio que utiliza las sesiones confiables, las siguientes consideraciones importantes debe tener en cuenta:

- Las sesiones confiables tienen estado y el estado se mantiene en el AppDomain. Esto significa que todos los mensajes que forman parte de una sesión confiable se deben procesar en el mismo AppDomain. Granjas de servidores Web y hospedajes donde el tamaño de la granja de servidores o el jardín es mayor que un nodo no pueden garantizar esta restricción.

- Las sesiones confiables que usan canales HTTP duales (por ejemplo, mediante `WsDualHttpBinding`) pueden requerir más el valor predeterminado de dos conexiones HTTP por cliente. Esto significa que una sesión dúplex confiable puede requerir hasta dos conexiones por cada lado, dado que los mensajes de protocolos y aplicaciones simultáneos que pueden transferir cada forma en un momento dado. Bajo ciertas condiciones según el patrón de intercambio de mensajes del servicio, esto significa que es posible interbloquear un servicio hospedado en web con HTTP dual y sesiones confiables. Para aumentar el número de conexiones HTTP permitidas por cliente, agregue lo siguiente al archivo de configuración pertinente (por ejemplo, *web.config* del servicio en cuestión):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  El valor de la `maxconnection` atributo es el número de conexiones necesarias. En este caso, el mínimo debe ser cuatro conexiones.
