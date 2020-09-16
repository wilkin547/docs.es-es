---
title: Procedimiento para proteger mensajes dentro de sesiones confiables
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: cec9356467886be022d05ead55d5cb6ccddcd838
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558685"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Procedimiento para proteger mensajes dentro de sesiones confiables

En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada. Habilite una sesión segura y confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.

Este procedimiento está compuesto por tres tareas clave:

1. Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.

1. Requiera la seguridad de mensajes dentro de la sesión confiable.

1. Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.

Es importante en la primera tarea que el elemento de configuración de punto de conexión contenga un `bindingConfiguration` atributo que haga referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity` . [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Después, el elemento de configuración hace referencia a este nombre para habilitar las sesiones confiables estableciendo el `enabled` atributo del [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) elemento en `true` . Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.

Para obtener la copia de origen del ejemplo en el que se basa este procedimiento de configuración, vea la [sesión confiable de WS](../samples/ws-reliable-session.md).

Los elementos esenciales de la segunda tarea se logran estableciendo el `mode` atributo del **\<security>** elemento contenido en el **\<binding>** elemento del cliente y del servicio en `Message` .

Los elementos esenciales de la tercera tarea se logran estableciendo el `clientCredentialType` atributo del **\<message>** elemento contenido en el **\<security>** elemento del cliente y del servicio en `Certificate` .

> [!NOTE]
> Cuando se usa la seguridad de mensajes con sesiones confiables, la mensajería confiable intenta autenticar a un cliente no autenticado hasta que se agota el tiempo de espera en lugar de producir una excepción cuando se produce el primer error.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el servicio con un WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el cliente con un WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Establecer el modo y ClientCredentialType en la configuración

1. Agregue un elemento de enlace adecuado al [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración. En el siguiente ejemplo se agrega un [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

1. Agregue un **\<binding>** elemento y establezca su `name` atributo en un valor adecuado. En el ejemplo se usa el nombre `MessageSecurity` .

1. Agregue un **\<security>** elemento y establezca el `mode` atributo en `Message` .

1. Dentro del **\<security>** elemento, agregue un **\<message>** elemento y establezca el `clientCredentialType` atributo en `Certificate` .

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
