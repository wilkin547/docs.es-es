---
title: Protección de mensajes dentro de sesiones confiables
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: edff27fe9649387c1922c34e72ef59d615e52b90
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141663"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Protección de mensajes dentro de sesiones confiables

En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada. Habilite una sesión segura y confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.

Este procedimiento está compuesto por tres tareas clave:

1. Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.

1. Requiera la seguridad de mensajes dentro de la sesión confiable.

1. Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.

Es importante en la primera tarea que el elemento de configuración de punto de conexión contenga un `bindingConfiguration` atributo que haga referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity`. El [**enlace de\<** ](../../configure-apps/file-schema/wcf/bindings.md) elemento de configuración hace referencia a este nombre para habilitar sesiones confiables estableciendo el atributo `enabled` del elemento [ **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) en `true`. Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.

Para obtener la copia de origen del ejemplo en el que se basa este procedimiento de configuración, vea la [sesión confiable de WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Los elementos esenciales de la segunda tarea se logran estableciendo el atributo `mode` del elemento **\<security >** incluido en el elemento **> de enlace\<** del cliente y servicio que se va a `Message`.

Los elementos esenciales de la tercera tarea se logran estableciendo el atributo `clientCredentialType` del elemento **\<mensaje >** incluido en el elemento **\<Security >** del cliente y el servicio que se va a `Certificate`.

> [!NOTE]
> Cuando se usa la seguridad de mensajes con sesiones confiables, la mensajería confiable intenta autenticar a un cliente no autenticado hasta que se agota el tiempo de espera en lugar de producir una excepción cuando se produce el primer error.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el servicio con un WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el cliente con un WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Establecer el modo y ClientCredentialType en la configuración

1. Agregue un elemento de enlace adecuado al elemento [ **\<enlaces >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración. En el ejemplo siguiente se agrega un elemento [ **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) .

1. Agregue un **\<enlazar >** elemento y establezca su atributo `name` en un valor adecuado. En el ejemplo se utiliza el nombre `MessageSecurity`.

1. Agregue un elemento **\<security >** y establezca el atributo `mode` en `Message`.

1. En el elemento **\<> de seguridad** , agregue un elemento **\<> de mensaje** y establezca el atributo `clientCredentialType` en `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
