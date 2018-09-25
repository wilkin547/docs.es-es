---
title: Protección de mensajes dentro de sesiones confiables
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
author: BrucePerlerMS
ms.openlocfilehash: f3269dc96dee2d534a8dd6677abeb6afae8776bd
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47115105"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Protección de mensajes dentro de sesiones confiables

En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada. Habilitar una sesión segura y confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.

Este procedimiento está compuesto por tres tareas clave:

1. Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.

1. Requiera la seguridad de mensajes dentro de la sesión confiable.

1. Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.

Es importante en la primera tarea que el elemento de configuración de punto de conexión contienen un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity`. El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración, a continuación, hace referencia a este nombre para habilitar sesiones confiables estableciendo el `enabled` atributo de la [  **\<reliableSession >** ](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`. Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.

Para la copia de origen del ejemplo en el que se basa este procedimiento de configuración, consulte el [sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Los elementos esenciales de la segunda tarea se logran estableciendo el `mode` atributo de la  **\<seguridad >** elemento contenido en el  **\<enlace >** elemento del cliente y servicio a `Message`.

Los elementos esenciales de la tercera tarea se logran estableciendo el `clientCredentialType` atributo de la  **\<mensaje >** elemento contenido en el  **\<seguridad >** elemento del cliente y servicio a `Certificate`.

> [!NOTE]
> Si utiliza la seguridad de mensaje con sesiones confiables, mensajería confiable intenta autenticar a un cliente sin autenticar hasta que se produzca un tiempo de espera en lugar de producir una excepción tras el primer error.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el servicio con WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: Exchange mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar al cliente con un WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: Exchange mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Establecer el modo y ClientCredentialType en configuración

1. Agregar un elemento de enlace apropiado para la [  **\<enlaces >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración. En el ejemplo siguiente se agrega un [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

1. Agregar un  **\<enlace >** y establezca su `name` atributo en un valor adecuado. El ejemplo usa el nombre `MessageSecurity`.

1. Agregar un  **\<seguridad >** y establezca el `mode` atributo `Message`.

1. Dentro de la  **\<seguridad >** elemento, agregue un  **\<mensaje >** y establezca el `clientCredentialType` atribuir a `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
