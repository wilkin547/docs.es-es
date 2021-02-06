---
description: 'Más información sobre: procedimientos recomendados para sesiones confiables'
title: Procedimientos recomendados para lograr sesiones confiables
ms.date: 03/30/2017
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
ms.openlocfilehash: 4b05dd914d2c5b8ec7941417b727bec1e5b43ba4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643675"
---
# <a name="best-practices-for-reliable-sessions"></a>Procedimientos recomendados para lograr sesiones confiables

En este tema se describen los procedimientos recomendados para las sesiones confiables.

## <a name="setting-maxtransferwindowsize"></a>Establecimiento de MaxTransferWindowSize

Las sesiones confiables en Windows Communication Foundation (WCF) usan una ventana de transferencia para almacenar los mensajes en el cliente y el servicio. La propiedad configurable <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica cuántos mensajes puede contener la ventana de transferencia.

En el remitente, indica el número de mensajes que puede contener la ventana de transferencia mientras espera las confirmaciones. en el receptor, indica cuántos mensajes se almacenan en búfer para el servicio.

La elección del tamaño adecuado afecta a la eficacia de la red y a la capacidad óptima del servicio. En las secciones siguientes se detalla lo que se debe tener en cuenta al elegir un valor para esta propiedad y el impacto del valor.

El tamaño predeterminado de la ventana de transferencia es de ocho mensajes.

### <a name="efficient-use-of-the-network"></a>Uso eficaz de la red

En este contexto, el término *red* corresponde a todo lo que se usa como base de la comunicación entre un cliente (remitente) y un servicio (receptor). Esto incluye las conexiones de transporte y cualquier intermediario o puentes entre, incluidos los enrutadores SOAP o los proxies o firewalls HTTP.

El uso eficaz de la red garantiza el uso total de la capacidad de la red. La cantidad de datos que se pueden transferir por segundo a través de la red (*velocidad de datos*) y el tiempo necesario para transferir datos del remitente al receptor (*latencia*) afectan a la eficacia de la utilización de la red.

En el remitente, la propiedad <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica cuántos mensajes puede contener su ventana de transferencia mientras espera las confirmaciones. Si la latencia de red es alta y para garantizar un remitente de respuesta y un uso de red eficaz, debe aumentar el tamaño de la ventana de transferencia.

Por ejemplo, incluso si el remitente se mantiene con la velocidad de datos, la latencia puede ser alta si existen varios intermediarios entre el remitente y el receptor, o si los datos deben pasar a través de una red o un intermediario de pérdida. Por lo tanto, el remitente tiene que esperar las confirmaciones de los mensajes en su ventana de transferencia antes de aceptar los mensajes nuevos que se enviarán en la conexión. Cuanto menor sea el búfer con latencia alta, menor será la eficacia del uso de la red. Por otro lado, un tamaño demasiado alto de la ventana de transferencia puede afectar al servicio, ya que es posible que el servicio necesite alcanzar la alta tasa de datos enviados por el cliente.

### <a name="running-the-service-to-capacity"></a>Ejecución del servicio para la capacidad

En tanto que la red se utiliza de forma eficaz, lo ideal es que también quiera que el servicio se ejecute en una capacidad óptima. La propiedad de tamaño de la ventana de transferencia en el receptor indica cuántos mensajes puede almacenar en búfer el receptor. Este almacenamiento en búfer de mensajes no solo ayuda al control del flujo de la red, sino también permite al servicio ejecutarse a capacidad completa. Por ejemplo, si el búfer es un mensaje y los mensajes llegan más rápido de lo que el servicio puede procesar, es posible que la red elimine los mensajes y que la capacidad esté desperdiciada o infrautilizada.

El uso de un búfer aumenta la disponibilidad del servicio, ya que recibe y almacena en búfer un mensaje de forma simultánea mientras procesa los mensajes recibidos anteriormente.

Se recomienda usar el mismo `MaxTransferWindowSize` en el remitente y el receptor.

### <a name="enabling-flow-control"></a>Habilitar el control de flujo

El *control de flujo* es un mecanismo que garantiza que el remitente y el receptor mantienen el ritmo entre sí, es decir, que los mensajes se consumen y actúan con la rapidez con que se producen. El tamaño de la ventana de transferencia en el cliente y el servicio asegura que el remitente y receptor se encuentran dentro de una ventana razonable de sincronización.

Se recomienda establecer la propiedad <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> en `true` cuando se usa una sesión confiable entre un cliente WCF y un servicio WCF.

## <a name="setting-maxpendingchannels"></a>Establecimiento de MaxPendingChannels

Al escribir un servicio que permite la comunicación de sesión confiable de distintos clientes, es posible que muchos clientes establezcan una sesión confiable en el servicio al mismo tiempo. La respuesta del servicio en estas situaciones depende de la propiedad `MaxPendingChannels`.

Cuando el remitente crea un canal de sesión confiable en un receptor, un protocolo de enlace entre ellos establece una sesión confiable. Una vez establecida la sesión confiable, el canal se coloca en una cola de canales pendientes para que el servicio los acepte. La propiedad `MaxPendingChannels` indica cuántos canales pueden estar en este estado.

Es posible que el servicio esté en un estado en el que no pueda aceptar más canales. Si la cola está llena, se rechaza un intento de establecer una sesión confiable y el cliente debe volver a intentarlo.

También es posible que los canales pendientes de la cola permanezcan en la cola durante más tiempo. Mientras tanto, se puede producir un tiempo de espera de inactividad en la sesión confiable, lo que provoca que el canal pase a un estado de error.

Al escribir un servicio que servicios de varios clientes simultáneamente, debe establecer un valor adecuado para sus necesidades. Establecer un valor demasiado alto para la `MaxPendingChannels` propiedad afecta al espacio de trabajo.

El valor predeterminado de <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> es de cuatro canales.

## <a name="reliable-sessions-and-hosting"></a>Hospedaje y sesiones confiables

Cuando el Web hospeda un servicio que usa sesiones confiables, debe tener en cuenta las siguientes consideraciones importantes:

- Las sesiones confiables tienen estado y el estado se mantiene en el AppDomain. Esto significa que todos los mensajes que forman parte de una sesión confiable se deben procesar en el mismo AppDomain. Granjas de servidores web y jardines Web en los que el tamaño de la granja o el jardín es mayor que un nodo no puede garantizar esta restricción.

- Las sesiones confiables que usan canales HTTP duales (por ejemplo, mediante `WsDualHttpBinding` ) pueden requerir más que el valor predeterminado de dos conexiones http por cliente. Esto significa que una sesión confiable dúplex puede requerir hasta dos conexiones cada vez, ya que los mensajes de protocolo y de aplicación simultáneos pueden transferirse de cada forma en un momento dado. En determinadas condiciones, según el patrón de intercambio de mensajes del servicio, esto significa que es posible crear un interbloqueo de un servicio hospedado en Web mediante el uso de sesiones HTTP duales y confiables. Para aumentar el número de conexiones HTTP permitidas por cliente, agregue lo siguiente al archivo de configuración correspondiente (por ejemplo, *web.config* del servicio en cuestión):

  ```xml
  <configuration>
    <system.net>
      <connectionManagement>
        <add name="*" maxconnection="4" />
      </connectionManagement>
    </system.net>
  </configuration>
  ```

  El valor del `maxconnection` atributo es el número de conexiones necesarias. En este caso, el mínimo debe ser cuatro conexiones.
