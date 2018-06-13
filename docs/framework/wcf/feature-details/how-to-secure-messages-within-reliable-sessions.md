---
title: Protección de mensajes dentro de sesiones confiables
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4c320d74f7e7966bfa35c824dbe30da768cd1447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493248"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="d8ad3-102">Protección de mensajes dentro de sesiones confiables</span><span class="sxs-lookup"><span data-stu-id="d8ad3-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="d8ad3-103">En este tema se describen los pasos necesarios para habilitar la seguridad de mensajes para los mensajes intercambiados dentro de una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="d8ad3-104">Habilitar una sesión confiable y segura de manera imperativa mediante código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="d8ad3-105">Este procedimiento utiliza los archivos de configuración de servicio y cliente para habilitar la sesión segura y confiable.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="d8ad3-106">Este procedimiento está compuesto por tres tareas clave:</span><span class="sxs-lookup"><span data-stu-id="d8ad3-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="d8ad3-107">Especifique que el cliente y el servicio intercambien mensajes dentro de una sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="d8ad3-108">Requiera la seguridad de mensajes dentro de la sesión confiable.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="d8ad3-109">Especifique el tipo de credencial de cliente que debe utilizar el cliente para autenticarse en el servicio.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="d8ad3-110">Es importante en la primera tarea que el elemento de configuración de extremo contenga un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada (en este ejemplo) `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="d8ad3-111">El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración, a continuación, hace referencia a este nombre para habilitar sesiones confiables estableciendo la `enabled` atributo de la [  **\<reliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) elemento `true`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="d8ad3-112">Puede requerir que las garantías de entrega ordenada estén disponibles dentro de una sesión confiable estableciendo el atributo `ordered` en `true`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="d8ad3-113">Para la copia de origen del ejemplo en el que se basa este procedimiento de configuración, consulte la [sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="d8ad3-114">Los elementos esenciales de la segunda tarea se logran estableciendo la `mode` atributo de la  **\<seguridad >** los elementos en el  **\<enlace >** elemento del cliente y servicio `Message`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="d8ad3-115">Los elementos esenciales de la tercera tarea se logran estableciendo la `clientCredentialType` atributo de la  **\<mensaje >** los elementos en el  **\<seguridad >** elemento del cliente y servicio `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="d8ad3-116">Cuando se utiliza la seguridad de los mensajes con sesiones confiables, mensajería confiable intenta autenticar a un cliente sin autenticar hasta que se produzca un tiempo de espera en lugar de producir una excepción tras el primer error.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="d8ad3-117">Configurar el servicio con WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="d8ad3-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="d8ad3-118">Este procedimiento se describe en [Cómo: intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="d8ad3-119">Configurar al cliente con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="d8ad3-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="d8ad3-120">Este procedimiento se describe en [Cómo: intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="d8ad3-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="d8ad3-121">Establecer el modo y ClientCredentialType en configuración</span><span class="sxs-lookup"><span data-stu-id="d8ad3-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="d8ad3-122">Agregar un elemento de enlace apropiado para la [  **\<enlaces >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="d8ad3-123">En el ejemplo siguiente se agrega un [  **\<wsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="d8ad3-124">Agregar un  **\<enlace >** y establezca su `name` de atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="d8ad3-125">En el ejemplo se usa el nombre `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="d8ad3-126">Agregar un  **\<seguridad >** y establezca el `mode` atribuir a `Message`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="d8ad3-127">En el  **\<seguridad >** elemento, agregar un  **\<mensaje >** y establezca el `clientCredentialType` atribuir a `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="d8ad3-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
