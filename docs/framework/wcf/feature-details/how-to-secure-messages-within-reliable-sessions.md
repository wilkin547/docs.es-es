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
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="d32f5-102">Procedimiento para proteger mensajes dentro de sesiones confiables</span><span class="sxs-lookup"><span data-stu-id="d32f5-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="d32f5-103">En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d32f5-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="d32f5-104">Habilite una sesión segura y confiable de manera imperativa mediante el uso de código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d32f5-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="d32f5-105">Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.</span><span class="sxs-lookup"><span data-stu-id="d32f5-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="d32f5-106">Este procedimiento está compuesto por tres tareas clave:</span><span class="sxs-lookup"><span data-stu-id="d32f5-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="d32f5-107">Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="d32f5-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="d32f5-108">Requiera la seguridad de mensajes dentro de la sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="d32f5-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="d32f5-109">Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.</span><span class="sxs-lookup"><span data-stu-id="d32f5-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="d32f5-110">Es importante en la primera tarea que el elemento de configuración de punto de conexión contenga un `bindingConfiguration` atributo que haga referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="d32f5-111">[**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Después, el elemento de configuración hace referencia a este nombre para habilitar las sesiones confiables estableciendo el `enabled` atributo del [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) elemento en `true` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="d32f5-112">Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.</span><span class="sxs-lookup"><span data-stu-id="d32f5-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="d32f5-113">Para obtener la copia de origen del ejemplo en el que se basa este procedimiento de configuración, vea la [sesión confiable de WS](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="d32f5-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="d32f5-114">Los elementos esenciales de la segunda tarea se logran estableciendo el `mode` atributo del **\<security>** elemento contenido en el **\<binding>** elemento del cliente y del servicio en `Message` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="d32f5-115">Los elementos esenciales de la tercera tarea se logran estableciendo el `clientCredentialType` atributo del **\<message>** elemento contenido en el **\<security>** elemento del cliente y del servicio en `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="d32f5-116">Cuando se usa la seguridad de mensajes con sesiones confiables, la mensajería confiable intenta autenticar a un cliente no autenticado hasta que se agota el tiempo de espera en lugar de producir una excepción cuando se produce el primer error.</span><span class="sxs-lookup"><span data-stu-id="d32f5-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="d32f5-117">Configurar el servicio con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="d32f5-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="d32f5-118">Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="d32f5-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="d32f5-119">Configurar el cliente con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="d32f5-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="d32f5-120">Este procedimiento se describe en [Cómo: intercambiar mensajes dentro de una sesión confiable](how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="d32f5-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="d32f5-121">Establecer el modo y ClientCredentialType en la configuración</span><span class="sxs-lookup"><span data-stu-id="d32f5-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="d32f5-122">Agregue un elemento de enlace adecuado al [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d32f5-122">Add an appropriate binding element to the [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="d32f5-123">En el siguiente ejemplo se agrega un [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d32f5-123">The following example adds a [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="d32f5-124">Agregue un **\<binding>** elemento y establezca su `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="d32f5-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="d32f5-125">En el ejemplo se usa el nombre `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="d32f5-126">Agregue un **\<security>** elemento y establezca el `mode` atributo en `Message` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="d32f5-127">Dentro del **\<security>** elemento, agregue un **\<message>** elemento y establezca el `clientCredentialType` atributo en `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="d32f5-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
