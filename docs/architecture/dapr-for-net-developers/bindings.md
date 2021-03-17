---
title: El bloque de creación de enlaces de DAPR
description: Descripción del bloque de creación de enlaces, sus características, ventajas y cómo aplicarlo
author: edwinvw
ms.date: 02/17/2021
ms.openlocfilehash: d6f8b2aa90b15e5b9cd7b5c29938660d1b2907e9
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623959"
---
# <a name="the-dapr-bindings-building-block"></a>El bloque de creación de enlaces de DAPR

Las ofertas sin *servidor* basadas en la nube, como Azure functions y AWS lambda, han adquirido una adopción amplia en el espacio de la arquitectura distribuida. Entre muchas ventajas, permiten que un microservicio *controle eventos desde* o *invoquen eventos en* un sistema externo, lo que abstrae la complejidad subyacente y los problemas de establecimiento. Los recursos externos son muchos: incluyen almacenes de almacenamiento de los mismos, sistemas de mensajes y recursos Web, en diferentes plataformas y proveedores. El [bloque de creación de enlaces DAPR](https://docs.dapr.io/developing-applications/building-blocks/bindings/bindings-overview/) aporta estas mismas capacidades de enlace de recursos a la Doorstep de las aplicaciones DAPR.

## <a name="what-it-solves"></a>Qué resuelve

Los enlaces de recursos DAPR permiten a los servicios integrar las operaciones empresariales en los recursos externos fuera de la aplicación inmediata. Un evento de un sistema externo podría desencadenar una operación en el servicio pasando información contextual. Después, el servicio podría expandir la operación desencadenando un evento en otro sistema externo, pasando la información de carga contextual. El servicio se comunica sin necesidad de acoplamiento o reconocimiento del recurso externo. La fontanería se encapsula dentro de los componentes de DAPR predefinidos. El componente DAPR que se va a usar puede intercambiarse fácilmente en tiempo de ejecución sin cambios de código.

Considere, por ejemplo, una cuenta de Twitter que desencadene un evento cada vez que un usuario Tweet una palabra clave. El servicio expone un controlador de eventos que recibe y procesa el tweet. Una vez completado, el servicio desencadena un evento que invoca un servicio externo Twilio. Twilio envía un mensaje SMS que incluye el tweet. En la figura 8-1 se muestra la arquitectura conceptual de esta operación.

![Enlace de entrada](media/bindings/bindings-architecture.png)

**Figura 8-1**. Arquitectura conceptual de un enlace de recursos DAPR.

A primera vista, el comportamiento del enlace de recursos puede ser similar al [patrón de publicación/suscripción](publish-subscribe.md) descrito anteriormente en este libro. Aunque comparten similitudes, hay diferencias. La publicación o suscripción se centra en la comunicación asincrónica entre DAPR Services. El enlace de recursos tiene un ámbito mucho más amplio. Se centra en la interoperabilidad del sistema entre las plataformas de software. Intercambio de información entre aplicaciones, almacenes de datos y servicios dispares fuera de la aplicación de microservicios.

## <a name="how-it-works"></a>Cómo funciona

El enlace de recursos DAPR comienza con un archivo de configuración de componentes. Este archivo YAML describe el tipo de recurso al que se enlazará junto con sus valores de configuración. Una vez configurado, el servicio puede recibir eventos del recurso o desencadenar eventos en él.

> [!NOTE]
> Las configuraciones de enlace se presentan en detalle más adelante en la sección *componentes* .

### <a name="input-bindings"></a>Enlaces de entrada

Los enlaces de entrada desencadenan el código con eventos entrantes de recursos externos. Para recibir eventos y datos, se registra un punto de conexión público desde el servicio que se convierte en el *controlador de eventos*. En la figura 8-2 se muestra el flujo:

![DAPR flujo de enlace de entrada](media/bindings/input-binding-flow.png)

**Figura 8-2**. Flujo de enlace de entrada DAPR.

En la figura 8,2 se describen los pasos para recibir eventos de una cuenta de Twitter externa:

1. El sidecar de DAPR lee el archivo de configuración de enlace y se suscribe al evento especificado para el recurso externo. En el ejemplo, el origen del evento es una cuenta de Twitter.
1. Cuando se publica un tweet coincidente en Twitter, el componente de enlace que se ejecuta en el sidecar de DAPR lo recoge y desencadena un evento.
1. El sidecar de DAPR invoca el punto de conexión (es decir, el controlador de eventos) configurado para el enlace. En el ejemplo, el servicio escucha una solicitud HTTP POST en el `/tweet` extremo en el puerto 6000. Dado que se trata de una operación POST de HTTP, la carga de JSON para el evento se pasa en el cuerpo de la solicitud.
1. Después de controlar el evento, el servicio devuelve un código de Estado HTTP `200 OK` .

El siguiente controlador de ASP.NET Core proporciona un ejemplo de cómo controlar un evento desencadenado por el enlace de Twitter:

```csharp
[ApiController]
public class SomeController : ControllerBase
{
    public class TwitterTweet
    {
        [JsonPropertyName("id_str")]
        public string ID {get; set; }

        [JsonPropertyName("text")]
        public string Text {get; set; }
    }

    [HttpPost("/tweet")]
    public ActionResult Post(TwitterTweet tweet)
    {
        // Handle tweet
        Console.WriteLine("Tweet received: {0}: {1}", tweet.ID, tweet.Text);

        // ...

        // Acknowledge message
        return Ok();
    }
}
```

Si la operación debe generar un error, se devolverá el código de Estado HTTP de nivel 400 o 500 adecuado. En el caso de los enlaces que incluyen garantías de *entrega una vez como mínimo* , el sidecar de DAPR volverá a intentar el desencadenador. Consulte [documentación de DAPR para enlaces de recursos] [1] para ver si ofrecen garantías de entrega *al menos una vez* o *exactamente una vez* .

### <a name="output-bindings"></a>Enlaces de salida

DAPR también incluye capacidades de *enlace de salida* . Permiten que el servicio desencadene un evento que invoca un recurso externo. De nuevo, empieza por configurar un archivo de configuración de enlace YAML que describe el enlace de salida. Una vez en su lugar, se desencadena un evento que invoca la API de enlaces en el sidecar de DAPR de la aplicación. En la figura 8-3 se muestra el flujo de un enlace de salida:

![Flujo de enlace de salida de DAPR](media/bindings/output-binding-flow.png)

**Figura 8-3**. Flujo de enlace de salida de DAPR.

1. El sidecar de DAPR lee el archivo de configuración de enlace con la información sobre cómo conectarse al recurso externo. En el ejemplo, el recurso externo es una cuenta de SMS de Twilio.
1. La aplicación invoca el `/v1.0/bindings/sms` punto de conexión en el sidecar de DAPR. En este caso, usa HTTP POST para invocar la API. También es posible usar gRPC.
1. El componente de enlace que se ejecuta en el sidecar de DAPR llama al sistema de mensajería externo para enviar el mensaje. El mensaje contendrá la carga que se pasa en la solicitud POST.

Por ejemplo, puede invocar un enlace de salida mediante la invocación de la API de DAPR con rizo:

```console
curl -X POST http://localhost:3500/v1.0/bindings/sms \
  -H "Content-Type: application/json" \
  -d '{
        "data": "Welcome to this awesome service",
        "metadata": {
          "toNumber": "555-3277"
        },
        "operation": "create"
      }'
```

Tenga en cuenta que el puerto HTTP es el mismo que el usado por el sidecar DAPR (en este caso, el puerto HTTP predeterminado DAPR `3500` ).

La estructura de la carga (es decir, el mensaje enviado) variará según el enlace. En el ejemplo anterior, la carga útil contiene un `data` elemento con un mensaje. Los enlaces a otros tipos de recursos externos pueden ser diferentes, especialmente para los metadatos que se envían. Cada carga útil también debe contener un `operation` campo, que define la operación que se ejecutará en el enlace. En el ejemplo anterior se especifica una `create` operación que crea el mensaje SMS. Entre las operaciones comunes se incluyen:

- create
- get
- delete
- list

Es el autor del enlace qué operaciones admite el enlace. La documentación de cada enlace describe las operaciones disponibles y cómo invocarlas.

## <a name="using-the-dapr-net-sdk"></a>Uso del SDK de .NET de DAPR

El SDK de .NET para DAPR proporciona compatibilidad específica del lenguaje para los desarrolladores de .NET Core. En el ejemplo siguiente, la llamada a `HttpClient.PostAsync()` se reemplaza con el `DaprClient.InvokeBindingAsync()` método. Este método especializado simplifica la invocación de un enlace de salida configurado:

```csharp
private async Task SendSMSAsync([FromServices] DaprClient daprClient)
{
    var message = "Welcome to this awesome service";
    var metadata = new Dictionary<string, string>
    {
      { "toNumber", "555-3277" }
    };
    await daprClient.InvokeBindingAsync("sms", "create", message, metadata);
}
```

El método espera los `metadata` valores y `message` .

Cuando se usa para invocar un enlace, `DaprClient` usa gRPC para llamar a la API de DAPR en el sidecar de DAPR.

## <a name="binding-components"></a>Enlazar componentes

En el capó, los enlaces de recursos se implementan con componentes de enlace DAPR. Los aporta la comunidad y están escritos en Go. Si tiene que integrarse con un recurso externo para el que aún no existe ningún enlace DAPR, puede crearlo usted mismo. Consulte el [repositorio de componentes de DAPR-entrib](https://github.com/dapr/components-contrib) para ver cómo puede contribuir con un enlace.

> [!NOTE]
> DAPR y todos sus componentes se escriben en el lenguaje [Golang](https://golang.org/) (Go). Go se considera una plataforma moderna de programación nativa en la nube.

Los enlaces se configuran mediante un archivo de configuración YAML. A continuación se muestra un ejemplo de configuración para el enlace de Twitter:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: twitter-mention
  namespace: default
spec:
  type: bindings.twitter
  version: v1
  metadata:
  - name: consumerKey
    value: "****" # twitter api consumer key, required
  - name: consumerSecret
    value: "****" # twitter api consumer secret, required
  - name: accessToken
    value: "****" # twitter api access token, required
  - name: accessSecret
    value: "****" # twitter api access secret, required
  - name: query
    value: "dapr" # your search query, required
```

Cada configuración de enlace contiene un `metadata` elemento general con `name` un `namespace` campo y. DAPR determinará el punto de conexión para invocar su servicio según el `name` campo configurado. En el ejemplo anterior, DAPR invocará el método anotado con `/twitter-mention` en el servicio cuando se produce un evento.

En el `spec` elemento, especifique el `type` del enlace junto con el enlace específico `metadata` . En el ejemplo se especifican las credenciales para acceder a una cuenta de Twitter mediante su API. Los metadatos pueden diferir entre los enlaces de entrada y salida. Por ejemplo, para usar Twitter como enlace de entrada, debe especificar el texto que se va a buscar en los tweets mediante el `query` campo. Cada vez que se envía un tweet coincidente, el sidecar de DAPR invocará el `/twitter-mention` punto de conexión en el servicio. También proporcionará el contenido del Tweet.

Se puede configurar un enlace para la entrada, la salida o ambos. Curiosamente, el enlace no especifica explícitamente la configuración de entrada o de salida. En su lugar, la dirección se deduce por el uso del enlace junto con los valores de configuración.

La [documentación de DAPR para los enlaces de recursos] [1] proporciona una lista completa de los enlaces disponibles y sus valores de configuración específicos.

### <a name="cron-binding"></a>Enlace cron

Preste mucha atención al enlace cron de DAPR. No se suscribe a eventos de un sistema externo. En su lugar, este enlace utiliza una programación de intervalo configurable para desencadenar la aplicación. El enlace proporciona una manera sencilla de implementar un trabajador en segundo plano para reactivarse y realizar algún trabajo a intervalos regulares, sin necesidad de implementar un bucle interminable con un retraso configurable. Este es un ejemplo de una configuración de enlace cron:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: checkOrderBacklog
  namespace: default
spec:
  type: bindings.cron
  version: v1
  metadata:
  - name: schedule
    value: "@every 30m"
```

En este ejemplo, DAPR desencadena un servicio mediante la invocación del `/checkOrderBacklog` punto de conexión cada 30 minutos. Hay varios patrones disponibles para especificar el `schedule` valor. Para obtener más información, consulte la [documentación de enlace de cron](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/cron/).

## <a name="reference-application-eshopondapr"></a>Aplicación de referencia: eShopOnDapr

La aplicación de referencia eShopOnDapr adjunta implementa un ejemplo de enlace de salida. Desencadena el enlace de [SendGrid](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/sendgrid/) de DAPR para enviar un correo electrónico al usuario cuando se coloca un nuevo pedido. Puede encontrar este enlace en el `eshop-email.yaml` archivo de la carpeta componentes:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: sendmail
  namespace: eshop
spec:
  type: bindings.twilio.sendgrid
  version: v1
  metadata:
  - name: apiKey
    secretKeyRef:
      name: sendGridAPIKey
auth:
  secretStore: eshop-secretstore
```

Esta configuración usa el componente de enlace [Twilio SendGrid](https://github.com/dapr/components-contrib/tree/master/bindings/twilio) . Observe cómo la clave de API para conectarse al servicio consume una referencia secreta de DAPR. Este enfoque mantiene los secretos fuera del archivo de configuración. Lea el [capítulo](secrets.md) sobre el bloque de creación de secretos para obtener más información sobre los secretos de DAPR.

La configuración de enlace especifica un componente de enlace que se puede invocar mediante el `/sendmail` punto de conexión en el sidecar de DAPR. A continuación se muestra un fragmento de código en el que se envía un correo electrónico cada vez que se inicia un pedido:

```csharp
public Task Handle(OrderStartedDomainEvent notification, CancellationToken cancellationToken)
{
    var string message = CreateEmailBody(notification);
    var metadata = new Dictionary<string, string>
    {
        {"emailFrom", "eShopOn@dapr.io"},
        {"emailTo", notification.UserName},
        {"subject", $"Your eShopOnDapr order #{notification.Order.Id}"}
    };
    return _daprClient.InvokeBindingAsync("sendmail", "create", message, metadata, cancellationToken);
}
```

Como puede ver en este ejemplo, `message` contiene el cuerpo del mensaje. El `CreateEmailBody` método simplemente da formato a una cadena con el texto del cuerpo. `metadata`Especifica el remitente de correo electrónico, el destinatario y el asunto del mensaje de correo electrónico. Si estos valores son estáticos, también se pueden incluir en los campos de metadatos del archivo de configuración. El nombre del enlace que se va a invocar es `sendmail` y la operación es `create` .

## <a name="summary"></a>Resumen

Los enlaces de recursos DAPR permiten la integración con distintos sistemas y recursos externos sin tener que tomar dependencias en sus bibliotecas o SDK. Estos sistemas externos no tienen por qué ser sistemas de mensajería como un bus de servicio o un agente de mensajes. Los enlaces también existen para almacenes de almacén de y recursos web como Twitter o SendGrid.

Los enlaces de entrada (o desencadenadores) reaccionan a los eventos que se producen en un sistema externo. Invocan los puntos de conexión HTTP públicos preconfigurados en la aplicación. DAPR usa el nombre del enlace en la configuración para determinar el punto de conexión al que llamar en la aplicación.

Los enlaces de salida enviarán mensajes a un sistema externo. Desencadena un enlace de salida mediante una solicitud HTTP POST en el `/v1.0/bindings/<binding-name>` punto de conexión en el sidecar de DAPR. También puede usar gRPC para invocar el enlace. El SDK de .NET ofrece un `InvokeBindingAsync` método para invocar enlaces de DAPR con gRPC.

Un enlace se implementa con un componente DAPR. Estos componentes son aportados por la comunidad. La configuración de cada componente de enlace tiene metadatos específicos para el sistema externo que abstrae. Además, los comandos que admite y la estructura de la carga variarán en función del componente de enlace.

### <a name="references"></a>Referencias

- [Documentación de DAPR para enlaces de recursos](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/)

>[!div class="step-by-step"]
>[Anterior](publish-subscribe.md)
>[Siguiente](observability.md)
