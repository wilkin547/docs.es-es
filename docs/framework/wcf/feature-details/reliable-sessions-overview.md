---
description: 'Más información acerca de: Introducción a las sesiones confiables'
title: Información general de sesiones confiables
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: 51de6012245b4fc0a367069d02fe69ee031f2b30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632898"
---
# <a name="reliable-sessions-overview"></a>Información general de sesiones confiables

La mensajería confiable SOAP de Windows Communication Foundation (WCF) proporciona confiabilidad de transferencia de mensajes de un extremo a otro entre los extremos SOAP. Hace esto en redes que no son confiables superando errores de transporte y errores del nivel de mensajes SOAP. En particular, proporciona una entrega basada en sesión, individual y (opcionalmente) ordenada de mensajes enviados a través de intermediarios de transporte o SOAP. La entrega basada en sesión permite agrupar los mensajes en una sesión con un orden opcional de los mensajes.

En este tema se describen las sesiones confiables, cómo y cuándo utilizarlas y cómo protegerlas.

## <a name="wcf-reliable-sessions"></a>Sesiones confiables de WCF

Las sesiones confiables de WCF son una implementación de mensajería confiable de SOAP, tal y como se define en el protocolo WS-ReliableMessaging.

La mensajería confiable de SOAP de WCF proporciona una sesión confiable de un extremo a otro entre dos extremos, independientemente del número o tipo de intermediarios que separan los extremos de la mensajería. Esto incluye cualquier intermediario de transporte que no utilice SOAP (por ejemplo, servidores proxy HTTP) o intermediarios que utilicen SOAP (por ejemplo, enrutadores o puentes basados en SOAP) necesarios para que los mensajes fluyan entre los extremos. Un canal de sesión confiable admite la comunicación *interactiva* para que los servicios conectados mediante este tipo de canal se ejecuten simultáneamente y intercambien y procesen mensajes en condiciones de baja latencia, es decir, en intervalos de tiempo relativamente cortos. Este acoplamiento significa que estos componentes hacen que el progreso sea conjunto o no juntos, por lo que no se proporciona ningún aislamiento entre ellos.

Una sesión confiable enmascara dos tipos de errores:

- Errores del nivel del mensaje de SOAP, que incluyen mensajes perdidos o duplicados y mensajes que llegan en un orden diferente del orden en el que se enviaron.

- Errores de transporte.

Una sesión confiable implementa el protocolo WS-ReliableMessaging y una ventana de transferencia en memoria para enmascarar errores del nivel de mensaje de SOAP y restablece las conexiones en caso de errores de transporte.

Una sesión confiable proporciona para los mensajes SOAP lo que el TCP proporciona para los paquetes de IP. Una conexión de socket de TCP proporciona una transferencia única, en orden de paquetes IP entre nodos. El canal confiable proporciona el mismo tipo de transferencia confiable, pero difiere de la confiabilidad de socket de TCP de las siguientes maneras:

- La confiabilidad se produce en el nivel de mensaje de SOAP, no para un paquete de tamaño aleatorio de bytes.

- La confiabilidad es independiente del transporte, no solo para la transferencia a través de TCP.

- La confiabilidad no está asociada a una sesión de transporte determinada (por ejemplo, la sesión que proporciona una conexión TCP) y puede usar varias sesiones de transporte simultáneamente o secuencialmente a lo largo de la duración de la sesión confiable.

- La sesión confiable se produce entre los puntos de conexión SOAP de envío y recepción, independientemente del número de conexiones de transporte requerido para la conectividad entre ellos. En Resumen, la confiabilidad TCP finaliza en la que finaliza la conexión de transporte, mientras que una sesión confiable proporciona confiabilidad de un extremo a otro.

## <a name="reliable-sessions-and-bindings"></a>Sesiones y enlaces confiables

Como se mencionó anteriormente, una sesión confiable es independiente del transporte. Además, puede establecer una sesión confiable en muchos patrones de intercambio de mensajes, como solicitud-respuesta o dúplex. Una sesión confiable de WCF se expone como una propiedad de un conjunto de enlaces.

Use una sesión confiable en los puntos de conexión que usan:

- Enlaces estándar de transporte basado en HTTP:

  - `WsHttpBinding` y exponen contratos de solicitud-respuesta o unidireccionales.

  - Cuando se usa una sesión confiable a través de un contrato de servicio unidireccional simple y de solicitud-respuesta.

  - `WsDualHttpBinding` y exponen contratos dúplex, de solicitud-respuesta o unidireccionales.

  - `WsFederationHttpBinding` y exponen contratos de solicitud-respuesta o unidireccionales.

- Enlaces estándar de transporte basado en TCP:

  - `NetTcpBinding` y exponen contratos dúplex, de solicitud-respuesta o unidireccionales.

Use una sesión confiable en cualquier otro enlace mediante la creación de un enlace personalizado, como HTTPS (para obtener más información acerca de los problemas, vea <a href="#reliable-sessions-and-security">sesiones confiables y seguridad</a>) o un enlace de canalización con nombre.

Puede apilar una sesión confiable en diferentes tipos de canales subyacentes y la forma de canal de sesión confiable resultante varía. Tanto en el cliente como en el servidor, el tipo de canal de sesión confiable compatible depende del tipo de canal subyacente utilizado. La siguiente tabla enumera los tipos de canales de sesión admitidos en el cliente como una función del tipo de canal subyacente.

| Tipos de canal de sesión confiables admitidos&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Sí               | Sí                      | Sí              | Sí                     |
| `IRequestSessionChannel`                        | Sí               | Sí                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | Sí              | Sí                     |

&#8224;los tipos de canal admitidos son los valores disponibles para el `TChannel` valor de parámetro genérico que se pasa al <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> método.

La siguiente tabla enumera los tipos de canales de sesión admitidos en el servidor como una función del tipo de canal subyacente.

| Tipos de canal de sesión confiables admitidos&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Sí             | Sí                    | Sí              | Sí                     |
| `IReplySessionChannel`                          | Sí             | Sí                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | Sí              | Sí                     |

&#8225;los tipos de canal admitidos son los valores disponibles para el `TChannel` valor de parámetro genérico que se pasa al <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> método.

## <a name="reliable-sessions-and-security"></a>Seguridad y sesiones confiables

La protección de una sesión confiable es importante para garantizar que las partes que se comunican (servicio y cliente) se autentiquen y que los mensajes intercambiados en la sesión no se manipulen. Además, es importante garantizar la integridad de cada sesión confiable individual. Una sesión confiable se protege mediante el enlace a un contexto de seguridad que se representa y administra mediante un canal de sesión de seguridad. El canal de seguridad proporciona una sesión de seguridad. Los tokens de seguridad intercambiados durante el establecimiento de la sesión se utilizan a continuación para proteger los mensajes de la sesión confiable.

Cuando una sesión confiable es a través de TCP-S, la sesión TCP está vinculada a la sesión confiable. Por lo tanto, la seguridad de transporte garantiza que la seguridad también está ligada a la sesión confiable. En este caso, se desactiva el restablecimiento de la conexión.

La única excepción se produce al utilizar HTTPS. La sesión de Capa de sockets seguros (SSL) no está enlazada a la sesión confiable. Esto impone una amenaza porque las sesiones que comparten un contexto de seguridad (la sesión SSL) no están protegidas entre sí; Esto puede ser o no una amenaza real en función de la aplicación.

## <a name="using-reliable-sessions"></a>Usar sesiones confiables

Para usar sesiones confiables de WCF, cree un punto de conexión con un enlace que admita una sesión confiable. Use uno de los enlaces proporcionados por el sistema que WCF proporciona con la sesión confiable habilitada o cree su propio enlace personalizado que lo hace.

Los enlaces definidos por el sistema que admiten y permiten de forma predeterminada una sesión confiable incluyen:

- <xref:System.ServiceModel.WSDualHttpBinding>

Los enlaces proporcionados por el sistema que admiten una sesión confiable como una opción, pero que no se habilitan de forma predeterminada incluyen:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Para obtener un ejemplo de cómo crear un enlace personalizado, consulte [Cómo: crear un enlace de sesión confiable personalizado con https](how-to-create-a-custom-reliable-session-binding-with-https.md).

Para obtener una explicación de los enlaces de WCF que admiten sesiones confiables, vea [enlaces proporcionados por el sistema](../system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Cuándo usar sesiones confiables

Es importante entender cuándo usar sesiones confiables en la aplicación. WCF admite sesiones confiables entre los extremos que están activos y activos al mismo tiempo. Si la aplicación requiere que uno de los extremos no esté disponible durante un período de tiempo, utilice las colas para lograr la confiabilidad.

Si el escenario requiere dos puntos de conexión conectados a través de TCP, es posible que TCP sea suficiente para proporcionar intercambios de mensajes confiables. Aunque no es necesario utilizar una sesión confiable, puesto que TCP garantiza que los paquetes llegan en orden y solo una vez.

Si el escenario tiene alguna de las siguientes características, debe considerar seriamente el uso de una sesión confiable.

- Intermediarios SOAP, como los enrutadores SOAP

- Intermediarios de proxy o puentes de transporte

- Conectividad intermitente

- Sesiones a través de HTTP

## <a name="see-also"></a>Vea también

- [Utilización de enlaces para configurar servicios y clientes](../using-bindings-to-configure-services-and-clients.md)
- [Sesión de confianza de WS](../samples/ws-reliable-session.md)
