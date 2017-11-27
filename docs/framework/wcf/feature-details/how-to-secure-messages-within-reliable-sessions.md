---
title: "Protección de mensajes dentro de sesiones confiables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3f27b1a4de2019660e0facb081300a79eae65b99
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a>Protección de mensajes dentro de sesiones confiables

En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada. Habilitar una sesión confiable y segura de manera imperativa mediante código o mediante declaración en el archivo de configuración. Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.

Este procedimiento está compuesto por tres tareas clave:

1. Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.

1. Requiera la seguridad de mensajes dentro de la sesión confiable.

1. Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.

Es importante en la primera tarea que el elemento de configuración de extremo contenga un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity`. El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración, a continuación, hace referencia a este nombre para habilitar sesiones confiables estableciendo la `enabled` atributo de la [  **\<reliableSession >** ](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`. Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.

Para la copia de origen del ejemplo en el que se basa este procedimiento de configuración, consulte la [sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

Los elementos esenciales de la segunda tarea se logran estableciendo la `mode` atributo de la  **\<seguridad >** los elementos en el  **\<enlace >** elemento del cliente y servicio `Message`.

Los elementos esenciales de la tercera tarea se logran estableciendo la `clientCredentialType` atributo de la  **\<mensaje >** los elementos en el  **\<seguridad >** elemento del cliente y servicio `Certificate`.

> [!NOTE]
> Cuando se utiliza la seguridad de los mensajes con sesiones confiables, mensajería confiable intenta autenticar a un cliente sin autenticar hasta que se produzca un tiempo de espera en lugar de producir una excepción tras el primer error.

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar el servicio con WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Configurar al cliente con un WSHttpBinding para utilizar una sesión confiable

Este procedimiento se describe en [Cómo: intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a>Establecer el modo y ClientCredentialType en configuración

1. Agregar un elemento de enlace apropiado para la [  **\<enlaces >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración. En el ejemplo siguiente se agrega un [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

1. Agregar un  **\<enlace >** y establezca su `name` de atributo en un valor adecuado. En el ejemplo se usa el nombre `MessageSecurity`.

1. Agregar un  **\<seguridad >** y establezca el `mode` atribuir a `Message`.

1. En el  **\<seguridad >** elemento, agregar un  **\<mensaje >** y establezca el `clientCredentialType` atribuir a `Certificate`.

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
