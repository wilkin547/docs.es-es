---
title: Información general de sesiones confiables
ms.date: 03/30/2017
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
ms.openlocfilehash: 6dd90ef800daf236d77c419d48c0857ac2d78aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962662"
---
# <a name="reliable-sessions-overview"></a>Información general de sesiones confiables

Mensajería confiable de SOAP de Windows Communication Foundation (WCF) proporciona confiabilidad de transferencia de mensajes de extremo a otro entre los extremos SOAP. Hace esto en redes que no son confiables superando errores de transporte y errores del nivel de mensajes SOAP. En particular, proporciona una entrega basada en sesión, individual y (opcionalmente) ordenada de mensajes enviados a través de intermediarios de transporte o SOAP. Proporciona entrega basada en sesiones para agrupar los mensajes en una sesión con una ordenación opcional de los mensajes.

En este tema se describe las sesiones confiables, cómo y cuándo utilizarlas y cómo protegerlos.

## <a name="wcf-reliable-sessions"></a>Sesiones confiables de WCF

Las sesiones confiables de WCF es una implementación de mensajería, tal como se define mediante el protocolo WS-ReliableMessaging confiable de SOAP.

Mensajería confiable de SOAP de WCF proporciona una sesión confiable-to-end entre dos puntos de conexión, independientemente del número o tipo de intermediarios que separan los puntos de conexión de mensajes. Esto incluye cualquier intermediario de transporte que no utilice SOAP (por ejemplo, servidores proxy HTTP) o intermediarios que utilicen SOAP (por ejemplo, los enrutadores basados en SOAP o puentes) que son necesarios para los mensajes fluir entre los puntos de conexión. Un canal de sesión confiable admite *interactivo* comunicación para que los servicios conectados mediante este tipo de canal se ejecutan simultáneamente y exchange y procesar mensajes bajo condiciones de baja latencia, es decir, dentro de relativamente corta intervalos de tiempo. Este acoplamiento significa que estos componentes progresan o dan error juntas, por lo que no hay ningún aislamiento proporcionado entre ellos.

Una sesión confiable enmascara dos tipos de errores:

- Errores del nivel del mensaje de SOAP, que incluyen mensajes perdidos o duplicados y mensajes que llegan en un orden diferente del orden en el que se enviaron.

- Errores de transporte.

Una sesión confiable implementa el protocolo WS-ReliableMessaging y una ventana de transferencia en memoria para enmascarar errores del nivel de mensaje de SOAP y restablece las conexiones en caso de errores de transporte.

Una sesión confiable proporciona para los mensajes SOAP lo que el TCP proporciona para los paquetes de IP. Una conexión de socket de TCP proporciona una transferencia única, en orden de paquetes IP entre nodos. El canal confiable proporciona el mismo tipo de transferencia confiable, pero difiere de la confiabilidad de socket de TCP de las siguientes maneras:

- La confiabilidad se produce en el nivel de mensaje de SOAP, no para un paquete de tamaño aleatorio de bytes.

- La confiabilidad es independiente del transporte, no solo para la transferencia a través de TCP.

- La confiabilidad no está vinculada a una sesión de transporte concreto (por ejemplo, la sesión proporciona una conexión TCP) y puede utilizar varias sesiones de transporte secuencialmente o simultáneamente durante la vigencia de la sesión confiable.

- La sesión confiable se produce entre los puntos de conexión SOAP de envío y recepción, independientemente del número de conexiones de transporte requerido para la conectividad entre ellos. En resumen, la confiabilidad TCP finaliza donde finaliza la conexión de transporte, mientras que una sesión confiable proporciona confiabilidad to-end.

## <a name="reliable-sessions-and-bindings"></a>Enlaces y sesiones confiables

Como se mencionó anteriormente, una sesión confiable es neutral de transporte. Además, puede establecer una sesión confiable sobre muchos patrones de intercambio de mensajes, como solicitud-respuesta o dúplex. Una sesión confiable de WCF se expone como una propiedad de un conjunto de enlaces.

Utilizar una sesión confiable en puntos de conexión que usen:

- Enlaces estándar de transporte basado en HTTP:

  - `WsHttpBinding` y exponen contratos de solicitud-respuesta o unidireccionales.

  - Cuando se usa la sesión confiable sobre un contrato de servicio unidireccional único o de solicitud-respuesta.

  - `WsDualHttpBinding` y exponen contratos dúplex, de solicitud-respuesta o unidireccionales.

  - `WsFederationHttpBinding` y exponen contratos de solicitud-respuesta o unidireccionales.

- Enlaces estándar de transporte basado en TCP:

  - `NetTcpBinding` y exponen contratos dúplex, de solicitud-respuesta o unidireccionales.

Utilizar una sesión confiable en cualquier otro enlace creando un enlace personalizado, como HTTPS (para obtener más información acerca de los problemas, consulte <a href="#reliable-sessions-and-security">las sesiones confiables y seguridad</a>) o un enlace de canalización con nombre.

Se puede apilar en una sesión confiable en diferentes tipos de canales subyacente y la forma de canal de sesión confiable resultante varía. En el cliente y el servidor, el tipo de canal de sesión confiable admitido depende del tipo de canal subyacente utilizado. La siguiente tabla enumera los tipos de canales de sesión admitidos en el cliente como una función del tipo de canal subyacente.

| Tipos de canal de sesión confiable admitidos&#8224; | `IRequestChannel` | `IRequestSessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :---------------: | :----------------------: | :--------------: | :---------------------: |
| `IOutputSessionChannel`                         | Sí               | Sí                      | Sí              | Sí                     |
| `IRequestSessionChannel`                        | Sí               | Sí                      | No               | No                      |
| `IDuplexSessionChannel`                         | No                | No                       | Sí              | Sí                     |

&#8224;Los tipos de canal admitidos son los valores disponibles para el tipo genérico `TChannel` valor de parámetro que se pasa a la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> método.

La siguiente tabla enumera los tipos de canales de sesión admitidos en el servidor como una función del tipo de canal subyacente.

| Tipos de canal de sesión confiable admitidos&#8225; | `IReplyChannel` | `IReplySessionChannel` | `IDuplexChannel` | `IDuplexSessionChannel` |
| ----------------------------------------------- | :-------------: | :--------------------: | :--------------: | :---------------------: |
| `IInputSessionChannel`                          | Sí             | Sí                    | Sí              | Sí                     |
| `IReplySessionChannel`                          | Sí             | Sí                    | No               | No                      |
| `IDuplexSessionChannel`                         | No              | No                     | Sí              | Sí                     |

&#8225;Los tipos de canal admitidos son los valores disponibles para el tipo genérico `TChannel` valor de parámetro que se pasa a la <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> método.

## <a name="reliable-sessions-and-security"></a>Seguridad y las sesiones confiables

Proteger una sesión confiable es importante asegurarse de que se autentiquen las partes en comunicación (servicio y cliente) y que no se manipule los mensajes intercambiados en la sesión. Además, es importante garantizar la integridad de cada sesión confiable. Una sesión confiable se protege enlazándola a un contexto de seguridad que se representa y administrado mediante un canal de sesión de seguridad. El canal de seguridad proporciona una sesión de seguridad. Los tokens de seguridad intercambiados durante el establecimiento de la sesión se utilizan a continuación para proteger los mensajes de la sesión confiable.

Cuando una sesión confiable es a través de TCP-S, la sesión TCP está ligada a la sesión confiable. Por lo tanto, la seguridad de transporte garantiza que la seguridad también esté ligada a la sesión confiable. En este caso, se desactiva el restablecimiento de la conexión.

La única excepción se produce al utilizar HTTPS. La sesión de capa de Sockets seguros (SSL) no está enlazada a la sesión confiable. Esto supone una amenaza porque las sesiones que comparten un contexto de seguridad (la sesión SSL) no están protegidas entre sí; Esto puede ser o no una amenaza real dependiendo de la aplicación.

## <a name="using-reliable-sessions"></a>Uso de sesiones confiables

Para utilizar sesiones confiables de WCF, cree un punto de conexión con un enlace que admita una sesión confiable. Use uno de los enlaces proporcionados por el sistema que proporciona WCF con la sesión confiable habilitada o crear su propio enlace personalizado que lo haga.

Los enlaces definidos por el sistema que admiten y permiten de forma predeterminada una sesión confiable incluyen:

- <xref:System.ServiceModel.WSDualHttpBinding>

Los enlaces proporcionados por el sistema que admiten una sesión confiable como una opción, pero no habilitan una de forma predeterminada son:

- <xref:System.ServiceModel.WSHttpBinding>

- <xref:System.ServiceModel.WSFederationHttpBinding>

- <xref:System.ServiceModel.NetTcpBinding>

Para obtener un ejemplo de cómo crear un enlace personalizado, vea [Cómo: Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

Para obtener una explicación de los enlaces de WCF que admiten sesiones confiables, vea [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).

## <a name="when-to-use-reliable-sessions"></a>Cuándo utilizar sesiones confiables

Es importante entender cuándo utilizar sesiones confiables en la aplicación. WCF admite sesiones confiables entre extremos que están activos y vivos al mismo tiempo. Si la aplicación requiere uno de los puntos de conexión no esté disponible para una duración de tiempo y luego usar colas para lograr la confiabilidad.

Si el escenario requiere dos extremos conectados a través de TCP, a continuación, TCP puede ser suficiente para proporcionar los intercambios de mensajes confiable. Aunque no es necesario utilizar una sesión confiable, puesto que TCP garantiza que los paquetes llegan en orden y solo una vez.

Si su escenario tiene cualquiera de las siguientes características, a continuación, debe considerar seriamente utilizar una sesión confiable.

- Intermediarios SOAP, como enrutadores SOAP

- Intermediarios proxy o puentes de transporte

- Conectividad intermitente

- Sesiones a través de HTTP

## <a name="see-also"></a>Vea también

- [Utilización de enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Sesión de confianza de WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md)
