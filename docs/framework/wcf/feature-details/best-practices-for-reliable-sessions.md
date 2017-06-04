---
title: "Procedimientos recomendados para lograr sesiones confiables | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b94f6e01-8070-40b6-aac7-a2cb7b4cb4f2
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Procedimientos recomendados para lograr sesiones confiables
En esta sección se discuten los procedimientos recomendados para obtener sesiones confiables.  
  
## Establecimiento de MaxTransferWindowSize  
 Las sesiones confiables en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizan una ventana de transferencia para retener los mensajes en el cliente y el servicio.  La propiedad configurable <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica cuántos mensajes puede contener la ventana de transferencia.  
  
 En el remitente esto indica cuántos mensajes puede contener la ventana de transferencia mientras espera las confirmaciones; en el receptor indica cuántos mensajes almacenar en búfer para el servicio.  
  
 La elección del tamaño adecuado afecta al nivel de eficacia de uso de la red y a la capacidad óptima en la que se ejecuta el servicio.  Las siguientes secciones describen qué es necesario tener en cuenta al elegir un valor para esta propiedad y el impacto de ese valor.  
  
 El tamaño predeterminado de la ventana de transferencia es de 8 mensajes.  
  
### Uso eficaz de la red  
 Aquí, el término *red* corresponde a todo lo que hay entre un cliente \(remitente\) y un servicio \(receptor\) utilizado como la base de comunicación.  Esto incluye las conexiones de transporte y cualquier intermediario o puentes que haya en medio, incluidos los enrutadores SOAP o proxys HTTP\/firewalls.  
  
 El uso eficaz de la red garantiza el uso total de la capacidad de la red.  La cantidad de datos que se pueden transferir por segundo sobre la red \(denominada *velocidad de datos*\) y el tiempo que tarda en transferir los datos desde el remitente hasta el receptor \(denominado *latencia*\) afectan a la eficacia de uso de la red.  
  
 En el remitente, la propiedad <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxTransferWindowSize%2A> indica cuántos mensajes puede contener su ventana de transferencia mientras espera las confirmaciones.  Por consiguiente, si la latencia de red es alta, para garantizar un remitente que responda y una utilización eficaz de la red, debería aumentar el tamaño de la ventana de la transferencia.  
  
 Por ejemplo, aun cuando el remitente se mantenga al ritmo de la velocidad de datos, la latencia podría ser alta si existen varios intermediarios entre el remitente y el receptor o un intermediario o red con pérdidas.  Por consiguiente, el remitente tiene que esperar las confirmaciones de los mensajes en su ventana de transferencia antes de aceptar nuevos mensajes que enviar a través de la conexión.  Mientras menos sea el búfer con una latencia alta, menos eficaz será el uso de la red.  Por otro lado, un tamaño demasiado grande de la ventana de la transferencia puede afectar al servicio, porque puede que éste tenga que alcanzar la alta velocidad de envío del cliente.  
  
### Ejecución del servicio a máxima capacidad  
 Todo lo eficazmente que se use la red, idealmente querrá que el servicio se ejecute a su capacidad óptima.  La propiedad de tamaño de la ventana de transferencia en el receptor indica cuántos mensajes puede almacenar en búfer el receptor.  Este almacenamiento en búfer de mensajes no solo ayuda al control del flujo de la red, sino también permite al servicio ejecutarse a capacidad completa.  Por ejemplo, si el búfer es 1 y los mensajes llegan antes de que el servicio pueda procesarlos, la red podría perder mensajes y podría sobre\- o infrautilizarse la capacidad de la red.  
  
 El uso de un búfer aumenta la disponibilidad del servicio, puesto que recibe y almacena en búfer el mensaje de manera concurrente, al mismo tiempo que procesa los mensajes recibidos anteriormente.  
  
 Se recomienda que utilice el mismo `MaxTransferWindowSize` en el remitente y receptor.  
  
### Permitir el control de flujo  
 El control de flujo es un mecanismo que asegura que el remitente y el receptor mantienen el ritmo del otro, es decir, que los mensajes se utilizan y se actúa sobre ellos según se generan.  El tamaño de la ventana de transferencia en el cliente y el servicio asegura que el remitente y receptor se encuentran dentro de una ventana razonable de sincronización.  
  
 Se recomienda encarecidamente que establezca la propiedad <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled%2A> en true al utilizar una sesión confiable entre un cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Establecimiento de MaxPendingChannels  
 Al escribir un servicio que habilita la comunicación de sesión confiable desde clientes diferentes, es posible hacer que muchos clientes establezcan una sesión confiable en el servicio al mismo tiempo.  La respuesta del servicio en estas situaciones depende de la propiedad `MaxPendingChannels`.  
  
 Cuando el remitente crea un canal de sesión confiable en un receptor, un protocolo de enlace entre ellos establece una sesión confiable.  Una vez establecida la sesión confiable, el canal se coloca en una cola de canales pendientes para que el servicio los acepte.  La propiedad `MaxPendingChannels` indica cuántos canales pueden estar en este estado.  
  
 Es posible que el servicio esté en un estado donde no pueda aceptar más canales.  Si la cola está llena, se rechaza un intento de establecer una sesión confiable y el cliente tiene que reintentarlo.  
  
 También es posible que los canales pendientes de la cola permanezcan en la cola durante más tiempo.  Entretanto, el tiempo de espera de inactividad en la sesión confiable puede aparecer, produciendo que el canal pase a un estado de error.  
  
 Por consiguiente, al escribir un servicio que se ocupa simultáneamente de varios clientes, debería establecer un valor que sea conveniente para sus necesidades.  Establecer un valor demasiado alto para la propiedad `MaxPendingChannels` afectará a su espacio de trabajo.  
  
 El valor predeterminado para <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.MaxPendingChannels%2A> es 4.  
  
## Hospedaje y sesiones confiables  
 Cuando se hospeda un servicio mediante web que utiliza sesiones confiables, debería tener en cuenta las siguientes consideraciones de importancia:  
  
-   Las sesiones confiables tienen estado y el estado se mantiene en el AppDomain.  Esto significa que todos los mensajes que forman parte de una sesión confiable se deben procesar en el mismo AppDomain.  Las granjas y jardines de servidores web donde el tamaño de la granja o el jardín sea \> 1 no podrán respetar esta restricción.  
  
-   Las sesiones confiables que usan canales HTTP duales \(por ejemplo, mediante `WsDualHttpBinding`\) pueden requerir más de las 2 conexiones HTTP predeterminadas por cliente.  Esto significa que una sesión dúplex confiable puede requerir hasta 2 conexiones por cada lado, puesto que se pueden transferir mensajes de protocolos y aplicaciones simultáneos en cualquier dirección en cualquier momento dado.  Esto significa que, bajo ciertas condiciones, dependiendo del patrón de intercambio de mensajes del servicio, es posible interbloquear un servicio hospedado por web utilizando sesiones confiables y HTTP dual.  Para aumentar el número de conexiones HTTP permitidas por cliente, agregue lo siguiente al archivo de configuración pertinente \(por ejemplo, web.config del servicio en cuestión\):  
  
```  
<configuration>  
   <system.net>  
      <connectionManagement>  
         <add name = "*" maxconnection = "XX" />  
      </connectionManagement>  
   </system.net>  
</configuration>  
```  
  
 Donde "XX" es el número de conexiones necesarias.  El mínimo en este caso debería ser 4.