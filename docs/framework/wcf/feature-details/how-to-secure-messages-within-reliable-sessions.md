---
description: 'Más información acerca de cómo: proteger mensajes dentro de sesiones confiables'
title: Procedimiento para proteger mensajes dentro de sesiones confiables
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: 73ca0d543edc2445dc72264e7eccf6c1eb616313
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643363"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="10722-103">Procedimiento para proteger mensajes dentro de sesiones confiables</span><span class="sxs-lookup"><span data-stu-id="10722-103">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="10722-104">En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="10722-104">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="10722-105">Habilite una sesión segura y confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="10722-105">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="10722-106">Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.</span><span class="sxs-lookup"><span data-stu-id="10722-106">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="10722-107">Este procedimiento está compuesto por tres tareas clave:</span><span class="sxs-lookup"><span data-stu-id="10722-107">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="10722-108">Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="10722-108">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="10722-109">Requiera la seguridad de mensajes dentro de la sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="10722-109">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="10722-110">Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.</span><span class="sxs-lookup"><span data-stu-id="10722-110">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="10722-111">Es importante en la primera tarea que el elemento de configuración de punto de conexión contenga un `bindingConfiguration` atributo que haga referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="10722-111">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="10722-112">[**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Después, el elemento de configuración hace referencia a este nombre para habilitar las sesiones confiables estableciendo el `enabled` atributo del [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) elemento en `true` .</span><span class="sxs-lookup"><span data-stu-id="10722-112">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="10722-113">Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.</span><span class="sxs-lookup"><span data-stu-id="10722-113">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="10722-114">Para obtener la copia de origen del ejemplo en el que se basa este procedimiento de configuración, vea la [sesión confiable de WS](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="10722-114">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="10722-115">Los elementos esenciales de la segunda tarea se logran estableciendo el `mode` atributo del **\<security>** elemento contenido en el **\<binding>** elemento del cliente y del servicio en `Message` .</span><span class="sxs-lookup"><span data-stu-id="10722-115">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="10722-116">Los elementos esenciales de la tercera tarea se logran estableciendo el `clientCredentialType` atributo del **\<message>** elemento contenido en el **\<security>** elemento del cliente y del servicio en `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="10722-116">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="10722-117">Cuando se usa la seguridad de mensajes con sesiones confiables, la mensajería confiable intenta autenticar a un cliente no autenticado hasta que se agota el tiempo de espera en lugar de producir una excepción cuando se produce el primer error.</span><span class="sxs-lookup"><span data-stu-id="10722-117">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="10722-118">Configurar el servicio con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="10722-118">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="10722-119">Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="10722-119">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="10722-120">Configurar el cliente con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="10722-120">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="10722-121">Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="10722-121">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="10722-122">Establecer el modo y ClientCredentialType en la configuración</span><span class="sxs-lookup"><span data-stu-id="10722-122">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="10722-123">Agregue un elemento de enlace adecuado al [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="10722-123">Add an appropriate binding element to the [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="10722-124">En el siguiente ejemplo se agrega un [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="10722-124">The following example adds a [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="10722-125">Agregue un **\<binding>** elemento y establezca su `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="10722-125">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="10722-126">En el ejemplo se usa el nombre `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="10722-126">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="10722-127">Agregue un **\<security>** elemento y establezca el `mode` atributo en `Message` .</span><span class="sxs-lookup"><span data-stu-id="10722-127">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="10722-128">Dentro del **\<security>** elemento, agregue un **\<message>** elemento y establezca el `clientCredentialType` atributo en `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="10722-128">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
