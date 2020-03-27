---
title: Configuración del registro de mensajes
ms.date: 03/30/2017
helpviewer_keywords:
- message logging [WCF]
ms.assetid: 0ff4c857-8f09-4b85-9dc0-89084706e4c9
ms.openlocfilehash: 283f43239d6cf5aea5ea668397a52313ff526e2a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345185"
---
# <a name="configuring-message-logging"></a>Configuración del registro de mensajes

En este tema se describe cómo puede configurar el registro de mensajes para distintos escenarios.

## <a name="enabling-message-logging"></a>Cómo habilitar el registro de mensajes

Windows Communication Foundation (WCF) no registra los mensajes de forma predeterminada. Para activar el registro de mensajes, debe agregar un agente de escucha de seguimiento al origen de seguimiento `System.ServiceModel.MessageLogging` y definir atributos para el elemento `<messagelogging>` en el archivo de configuración.

En el siguiente ejemplo, se muestra cómo habilitar el registro y especificar opciones adicionales.

```xml
<system.diagnostics>
  <sources>
    <source name="System.ServiceModel.MessageLogging">
      <listeners>
         <add name="messages"
              type="System.Diagnostics.XmlWriterTraceListener"
              initializeData="c:\logs\messages.svclog" />
        </listeners>
    </source>
  </sources>
</system.diagnostics>

<system.serviceModel>
  <diagnostics>
    <messageLogging
         logEntireMessage="true"
         logMalformedMessages="false"
         logMessagesAtServiceLevel="true"
         logMessagesAtTransportLevel="false"
         maxMessagesToLog="3000"
         maxSizeOfMessageToLog="2000"/>
  </diagnostics>
</system.serviceModel>
```

Para obtener más información acerca de la configuración de registro de mensajes, consulte [Configuración recomendada para el seguimiento y](./tracing/recommended-settings-for-tracing-and-message-logging.md)el registro de mensajes .

Puede utilizar `add` para especificar el nombre y tipo del agente de escucha que desea utilizar. En la configuración de ejemplo, el agente de escucha se denomina "mensajes" y agrega el agente de escucha de seguimiento de .NET Framework estándar (`System.Diagnostics.XmlWriterTraceListener`) como el tipo que se va a utilizar. Si utiliza `System.Diagnostics.XmlWriterTraceListener`, debe especificar la ubicación y el nombre del archivo de resultados en el archivo de configuración. Esto se hace estableciendo `initializeData` en el nombre del archivo de registro. De lo contrario, el sistema produce una excepción. También puede implementar un agente de escucha personalizado que emita registros en un archivo predeterminado.

> [!NOTE]
> Dado que el registro de mensajes accede al espacio en disco, debería limitar el número de mensajes que se escriben en el disco para un servicio determinado. Cuando se alcanza el límite de mensajes, se genera un seguimiento en el nivel de información y todas las actividades de registro de mensajes se detienen.

El nivel de registro, así como las opciones adicionales, se tratan en la sección Registro de niveles y opciones.

El atributo `switchValue` de `source` solo es válido para seguimientos. Si especifica un atributo `switchValue` para el origen de seguimiento `System.ServiceModel.MessageLogging` tal y como se indica a continuación, no tendrá ningún efecto.

```xml
<source name="System.ServiceModel.MessageLogging" switchValue="Verbose">
</source>
```

Si desea deshabilitar el origen de seguimiento, debería utilizar en su lugar los atributos `logMessagesAtServiceLevel`, `logMalformedMessages` y `logMessagesAtTransportLevel` del elemento `messageLogging`. Debería establecer todos estos atributos en `false`. Esta acción puede realizarse utilizando el archivo de configuración en el ejemplo de código anterior, mediante la interfaz del usuario del editor de configuración, o mediante WMI. Para obtener más información acerca de la herramienta Editor de configuración, vea Herramienta Editor de configuración [(SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md). Para obtener más información acerca de WMI, consulte Uso de Instrumental de administración de [Windows para diagnósticos](./wmi/index.md).

## <a name="logging-levels-and-options"></a>Registro de niveles y opciones

En el caso de los mensajes entrantes, el registro se produce inmediatamente después de que se haya formado el mensaje, inmediatamente antes de que el mensaje obtenga el código de usuario en el nivel de servicio y cuando se detecten los mensajes incorrectos.

En el caso de los mensajes salientes, el registro se produce inmediatamente después de que el mensaje deje el código de usuario e inmediatamente antes de que el mensaje esté en tránsito.

WCF registra los mensajes en dos niveles diferentes, servicio y transporte. Los mensajes incorrectos también se registran. Las tres categorías son independientes entre sí y pueden activarse por separado en la configuración.

Puede controlar el nivel de registro definiendo los atributos `logMessagesAtServiceLevel`, `logMalformedMessages` y `logMessagesAtTransportLevel` del elemento `messageLogging`.

### <a name="service-level"></a>Nivel de servicio

Los mensajes registrados en este nivel están a punto de introducir (al recibir) o dejar (al enviar) código de usuario. Si se han definido los filtros, solo se registrarán los mensajes que coincidan con los filtros. De lo contrario, se registrarán todos los mensajes en el nivel de servicio. Los mensajes de infraestructura (transacciones, canal del mismo nivel y seguridad) también se registran en este nivel, salvo los mensajes de la mensajería de confianza. En los mensajes transmitidos, solo se registran los encabezados. Además, los mensajes seguros se registran descifrados en este nivel.

### <a name="transport-level"></a>Nivel de transporte

Los mensajes registrados en este nivel están listos para ser codificados o descodificados para el transporte o para después de éste en tránsito. Si se han definido los filtros, solo se registrarán los mensajes que coincidan con los filtros. De lo contrario, se registrarán todos los mensajes en el nivel de transporte. Todos los mensajes de la infraestructura se registran en este nivel, incluidos los mensajes de la mensajería de confianza. En los mensajes transmitidos, solo se registran los encabezados. Además, los mensajes seguros se registran como cifrados en este nivel, excepto si se utiliza un transporte seguro como HTTPS.

### <a name="malformed-level"></a>Nivel incorrecto

Los mensajes con formato incorrecto son mensajes rechazados por la pila de WCF en cualquier etapa del procesamiento. Los mensajes con formato incorrecto se registran tal cual: cifrados si lo están, con XML inadecuado, etc. `maxSizeOfMessageToLog` definió el tamaño del mensaje que se debía registrar como CDATA. De forma predeterminada, `maxSizeOfMessageToLog` es igual a 256 K. Para obtener más información acerca de este atributo, consulte la sección Otras opciones.

### <a name="other-options"></a>Otras opciones

Además de los niveles del registro, el usuario puede especificar las opciones siguientes:

- Registro del mensaje completo (atributo `logEntireMessage`): este valor especifica si se registró el mensaje completo (encabezado y cuerpo del mensaje). El valor predeterminado es `false`, lo que significa que solo se registra el encabezado. Esta configuración afecta a los niveles de registro de mensajes de servicio y transporte.

- Número máximo de mensajes que registrar (atributo `maxMessagesToLog`): este valor especifica el número máximo de mensajes que se van a registrar. Se contarán todos los mensajes (servicio, transporte y mensajes incorrectos) hacia esta cuota. Cuando se alcance, se emitirá un seguimiento y no se registrará ningún mensaje adicional. El valor predeterminado es 10000.

- Tamaño máximo del mensaje que registrar (atributo `maxSizeOfMessageToLog`): este valor especifica el tamaño máximo de los mensajes que registrar en bytes. Los mensajes que superan el límite de tamaño no están registrados y no se realizará ninguna otra actividad para ese mensaje. Este valor afecta a todos los niveles de seguimiento. Si el seguimiento de ServiceModel está activado, se emitirá el seguimiento de nivel de advertencia en el primer punto de registro (ServiceModelSend * o TransportReceive) para notificar al usuario. El valor predeterminado para los mensajes de nivel de servicio y de transporte es 256 K, mientras que el valor predeterminado para los mensajes incorrectos es 4 K.

  > [!CAUTION]
  > El tamaño del mensaje que se calcula para comparar con el valor de `maxSizeOfMessageToLog` es el tamaño del mensaje en memoria antes de la serialización. Este tamaño puede diferir de la longitud real de la cadena del mensaje que está registrando y, en muchas ocasiones, es mayor que el tamaño real. Como resultado, es posible que los mensajes no estén registrados. Puede consignar este hecho al especificar el atributo `maxSizeOfMessageToLog` para que sea un 10% mayor que el tamaño del mensaje esperado. Además, si los mensajes incorrectos se registran, el espacio en disco real utilizado por los registros de los mensajes puede ser hasta 5 veces más que el tamaño del valor especificado por `maxSizeOfMessageToLog`.

Si ningún agente de escucha de seguimiento se define en el archivo de configuración, no se generará ninguna salida de registro sin tener en cuenta el nivel de registro especificado.

Las opciones de registro de mensajes, como los atributos descritos en esta sección, se pueden cambiar en el tiempo de ejecución mediante el Instrumental de administración de Windows (WMI). Esto se puede hacer accediendo a la instancia [de AppDomainInfo,](./wmi/appdomaininfo.md) que expone estas propiedades booleanas: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, y `LogMalformedMessages`. Por consiguiente, si configura un agente de escucha de traza para el registro de mensajes, pero define estas opciones en `false`, en la configuración, puede cambiarlas después a `true`, una vez se esté ejecutando la aplicación. Esto habilita en efecto el registro de mensajes en el tiempo de ejecución. De igual forma, si habilita el registro de mensajes en su archivo de configuración, puede deshabilitarlo en el tiempo de ejecución mediante WMI. Para obtener más información, consulte Uso de Instrumental de administración de [Windows para diagnósticos](./wmi/index.md).

El campo `source` de un registro de mensajes especifica en qué contexto se registra el mensaje: al enviar o recibir un mensaje de solicitud, para una solicitud-respuesta o una solicitud unidireccional, en el modelo de servicio o capa de transporte, o en el caso de un mensaje con formato incorrecto.

Para los mensajes `source` con `Malformed`formato incorrecto, es igual a . De lo contrario, el origen tiene los valores siguientes basados en el contexto.

Para solicitud/respuesta

||Enviar solicitud|Recibir solicitud|Enviar respuesta|Recibir respuesta|
|-|------------------|---------------------|----------------|-------------------|
|Nivel de modelo de servicio|web de Office<br /><br /> Nivel<br /><br /> Envío<br /><br /> Request|web de Office<br /><br /> Nivel<br /><br /> Recepción<br /><br /> Request|web de Office<br /><br /> Nivel<br /><br /> Envío<br /><br /> Reply|web de Office<br /><br /> Nivel<br /><br /> Recepción<br /><br /> Reply|
|Nivel de transporte|Transporte<br /><br /> Envío|Transporte<br /><br /> Recepción|Transporte<br /><br /> Envío|Transporte<br /><br /> Recepción|

Para solicitud unidireccional

||Enviar solicitud|Recibir solicitud|
|-|------------------|---------------------|
|Nivel de modelo de servicio|web de Office<br /><br /> Nivel<br /><br /> Envío<br /><br /> Datagrama|web de Office<br /><br /> Nivel<br /><br /> Recepción<br /><br /> Datagrama|
|Nivel de transporte|Transporte<br /><br /> Envío|Transporte<br /><br /> Recepción|

## <a name="message-filters"></a>Filtros de mensajes

Los filtros de mensajes se definen en el elemento de configuración `messageLogging` de la sección de configuración `diagnostics`. Se aplican en los niveles de servicio y transporte. Cuando se definen uno o más filtros, sólo se registran los mensajes que coinciden por lo menos con uno de los filtros. Si no se define ningún filtro, todos los mensajes atraviesan.

Los filtros admiten la sintaxis de XPath completa y se aplican en el orden que aparecen en el archivo de configuración. Un filtro con sintaxis incorrecta provoca una excepción de configuración.

Los filtros también proporcionan una característica de seguridad mediante el atributo `nodeQuota`, que limita el número máximo de nodos en Xpath DOM que se puede examinar para coincidir con el filtro.

El siguiente ejemplo muestra cómo configurar un filtro que solo graba mensajes que tienen una sección de encabezado SOAP.

```xml
<messageLogging logEntireMessage="true"
    logMalformedMessages="true"
    logMessagesAtServiceLevel="true"
    logMessagesAtTransportLevel="true"
    maxMessagesToLog="420">
    <filters>
        <add nodeQuota="10" xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
                 /soap:Envelope/soap:Header
        </add>
     </filters>
</messageLogging>
```

Los filtros no se pueden aplicar al cuerpo de un mensaje. Los filtros que intentan manipular el cuerpo de un mensaje se quitan de la lista de filtros. También se emite un evento que indica esto. Por ejemplo, el filtro siguiente se quitaría de la tabla de filtro.

```xml
<add xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">/s:Envelope/s:Body[contains(text(), "Hello")]</add>
```

## <a name="configuring-a-custom-listener"></a>Configuración de un agente de escucha personalizado

También puede configurar un agente de escucha personalizado con opciones adicionales. Un agente de escucha personalizado puede ser útil para filtrar los elementos PII específicos de la aplicación de los mensajes antes de registrar. El ejemplo siguiente muestra una configuración personalizada del agente de escucha.

```xml
<system.diagnostics>
   <sources>
     <source name="System.ServiceModel.MessageLogging">
           <listeners>
             <add name="MyListener"
                    type="YourCustomListener"
                    initializeData="c:\logs\messages.svclog"
                    maxDiskSpace="1000"/>
           </listeners>
     </source>
   </sources>
</system.diagnostics>
```

Debería tener en cuenta que el atributo `type` debería estar establecido en un nombre de ensamblado certificado del tipo.

## <a name="see-also"></a>Vea también

- [\<messageLogging>](../../configure-apps/file-schema/wcf/messagelogging.md)
- [Registro de mensajes](message-logging.md)
- [Configuración recomendada para el seguimiento y el registro de mensajes](./tracing/recommended-settings-for-tracing-and-message-logging.md)
