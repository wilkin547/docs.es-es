---
title: "Información general de sesiones confiables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6ca4b3e254055c7142259ea6022a53f003ea25f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions-overview"></a>Información general de sesiones confiables

La mensajería de confianza de SOAP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona confiabilidad de transferencia de mensajes de un extremo a otro entre los extremos de SOAP. Hace esto en redes que no son confiables superando errores de transporte y errores del nivel de mensajes SOAP. En particular, proporciona una entrega basada en sesión, individual y (opcionalmente) ordenada de mensajes enviados a través de intermediarios de transporte o SOAP. Proporciona entrega basada en sesión para agrupar los mensajes en una sesión con una ordenación opcional de los mensajes.

Este tema describe las sesiones confiables, cómo y cuándo utilizarlos y cómo protegerlos.

## <a name="wcf-reliable-sessions"></a>Sesiones confiables de WCF

Las sesiones confiables de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son una implementación de mensajería confiable de SOAP tal y como la define el protocolo WS-ReliableMessaging.

La mensajería confiable SOAP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una sesión confiable de un extremo a otro entre dos extremos, sin tener en cuenta el número o tipo de intermediarios que separan los extremos de la mensajería. Esto incluye a cualquier intermediario de transporte que no utilice SOAP (por ejemplo, los servidores proxy HTTP) o los intermediarios que utilicen SOAP (por ejemplo, enrutadores basados en SOAP o puentes) que son necesarios para los mensajes fluyan entre los puntos de conexión. Un canal de sesión confiable admite *interactivo* comunicación para que los servicios conectados mediante este tipo de canal se ejecutan simultáneamente y exchange y procesar mensajes bajo condiciones de baja latencia, es decir, en relativamente corto intervalos de tiempo. Este acoplamiento significa que estos componentes progresan o dan error juntas, así que no hay ningún aislamiento proporcionado entre ellos.

Una sesión confiable enmascara dos tipos de errores:

- Errores del nivel del mensaje de SOAP, que incluyen mensajes perdidos o duplicados y mensajes que llegan en un orden diferente del orden en el que se enviaron.

- Errores de transporte.

Una sesión confiable implementa el protocolo WS-ReliableMessaging y una ventana de transferencia en memoria para enmascarar errores del nivel de mensaje de SOAP y restablece las conexiones en caso de errores de transporte.

Una sesión confiable proporciona para los mensajes SOAP lo que el TCP proporciona para los paquetes de IP. Una conexión de socket de TCP proporciona una transferencia única, en orden de paquetes IP entre nodos. El canal confiable proporciona el mismo tipo de transferencia confiable, pero difiere de la confiabilidad de socket de TCP de las siguientes maneras:

- La confiabilidad se produce en el nivel de mensaje de SOAP, no para un paquete de tamaño aleatorio de bytes.

- La fiabilidad es independiente del transporte, no solo para la transferencia a través de TCP.

- La confiabilidad no está vinculada a una sesión de transporte concreto (por ejemplo, la sesión proporciona una conexión TCP) y puede utilizar varias sesiones de transporte secuencialmente o simultáneamente sobre la duración de la sesión confiable.

- La sesión confiable se produce entre los puntos de conexión SOAP de envío y recepción, independientemente del número de conexiones de transporte requerido para la conectividad entre ellos. En resumen, la confiabilidad TCP finaliza donde finaliza la conexión de transporte, mientras que una sesión confiable proporciona confiabilidad to-end.

## <a name="reliable-sessions-and-bindings"></a>Enlaces y sesiones confiables

Como se mencionó anteriormente, una sesión confiable es neutral de transporte. Además, puede establecer una sesión confiable sobre muchos patrones de intercambio de mensajes, como solicitud-respuesta o dúplex. A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sesión confiable se expone como una propiedad de un conjunto de enlaces.

Utilizar una sesión confiable en extremos que usan:

- Enlaces estándar de transporte basado en HTTP:

  - `WsHttpBinding` y exponen contratos de solicitud-respuesta o unidireccionales.

  - Cuando se usa la sesión confiable mediante una solicitud / respuesta o el contrato de servicio unidireccional único.

  - `WsDualHttpBinding` y exponen contratos dúplex, de solicitud-respuesta o unidireccionales.

  - `WsFederationHttpBinding` y exponen contratos de solicitud-respuesta o unidireccionales.

- Enlaces estándar de transporte basado en TCP:

  - `NetTcpBinding` y exponen contratos dúplex, de solicitud-respuesta o unidireccionales.

Utilizar una sesión confiable en cualquier otro enlace creando un enlace personalizado, como HTTPS (para obtener más información acerca de los problemas, consulte <a href="#reliable-sessions-and-security">las sesiones confiables y seguridad</a>) o un enlace de canalización con nombre.

Se puede apilar en una sesión confiable en diferentes tipos de canal subyacentes y la forma de canal de sesión confiable resultante varía. En el cliente y el servidor, el tipo de canal de sesión confiable admitido depende del tipo de canal subyacente que se utiliza. La siguiente tabla enumera los tipos de canales de sesión admitidos en el cliente como una función del tipo de canal subyacente.

| Admite tipos de canal de sesión confiable &#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Sí               | Sí                      | Sí              | Sí                     |
| `IRequestSessionChannel`                        | Sí               | Sí                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | Sí              | Sí                     |

&#8224; Los tipos de canal admitidos son los valores disponibles para la interfaz genérica `TChannel` valor de parámetro que se pasa a la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> método.

La siguiente tabla enumera los tipos de canales de sesión admitidos en el servidor como una función del tipo de canal subyacente.

| Admite tipos de canal de sesión confiable &#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Sí             | Sí                    | Sí              | Sí                     |
| `IReplySessionChannel`                          | Sí             | Sí                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | Sí              | Sí                     |

&#8225; Los tipos de canal admitidos son los valores disponibles para la interfaz genérica `TChannel` valor de parámetro que se pasa a la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> método.

## <a name="reliable-sessions-and-security"></a>Seguridad y sesiones confiables

Proteger una sesión confiable es importante para asegurarse de que se autentiquen las partes en comunicación (servicio y cliente) y que no se manipulen los mensajes intercambiados en la sesión. Además, es importante garantizar la integridad de cada sesión confiable. Una sesión confiable se protege enlazándola a un contexto de seguridad que se representa y administrado mediante un canal de sesión de seguridad. El canal de seguridad proporciona una sesión de seguridad. Los tokens de seguridad intercambiados durante el establecimiento de la sesión se utilizan a continuación para proteger los mensajes de la sesión confiable.

Cuando una sesión confiable se encuentra sobre TCP-S, la sesión TCP está ligada a la sesión confiable. Por lo tanto, la seguridad de transporte garantiza que la seguridad también esté ligada a la sesión confiable. En este caso, se desactiva el restablecimiento de la conexión.

La única excepción se produce al utilizar HTTPS. La sesión de capa de Sockets seguros (SSL) no está enlazada a la sesión confiable. Esto supone una amenaza porque las sesiones que comparten un contexto de seguridad (la sesión SSL) no se protegen entre sí; Esto puede o no constituir una amenaza real dependiendo de la aplicación.

## <a name="using-reliable-sessions"></a>Uso de sesiones confiables

Para utilizar sesiones confiables de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], cree un extremo con un enlace que admita una sesión confiable. Utilice uno de los enlaces proporcionados por el sistema que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona con la sesión confiable habilitada o cree su propio enlace personalizado que lo haga.

Los enlaces definidos por el sistema que admiten y permiten de forma predeterminada una sesión confiable incluyen:

- <xref:System.ServiceModel.WSDualHttpBinding>

Los enlaces proporcionados por el sistema que admiten una sesión confiable como una opción, pero no habilitan una de forma predeterminada son:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Para obtener un ejemplo de cómo crear un enlace personalizado, vea [Cómo: crear un enlace personalizado de la sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

Para obtener una explicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enlaces que admiten las sesiones confiables, consulte [enlaces proporcionados](../../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Cuándo utilizar sesiones confiables

Es importante entender cuándo utilizar sesiones confiables en la aplicación. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite sesiones confiables entre los extremos que están activos y en funcionamiento al mismo tiempo. Si la aplicación requiere uno de los extremos no esté disponible para una duración de tiempo, a continuación, usar las colas para lograr la confiabilidad.

Si el escenario requiere dos extremos que se conectan a través de TCP, puede que TCP sea suficiente para proporcionar los intercambios de mensajes confiables. Sin embargo, no es necesario utilizar una sesión confiable, puesto que TCP garantiza que los paquetes llegan en orden y solo una vez.

Si su escenario tiene cualquiera de las siguientes características, a continuación, debe considerar seriamente utilizar una sesión confiable.

- Intermediarios SOAP, como enrutadores SOAP

- Intermediarios proxy o puentes de transporte

- Errores de conectividad intermitentes

- Sesiones a través de HTTP

## <a name="see-also"></a>Vea también

[Utilización de enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
[Sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
