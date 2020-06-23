---
title: Procedimiento para establecer el modo de seguridad
description: 'Obtenga información sobre cómo establecer los tres modos de seguridad de WCF comunes en la mayoría de los enlaces predefinidos: Transport, Message y TransportWithMessageCredential.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 2f834e1930b7676592f6cbc29a577424d75ebc01
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244548"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="3eba7-103">Procedimiento para establecer el modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="3eba7-103">How to: Set the Security Mode</span></span>

<span data-ttu-id="3eba7-104">La seguridad de Windows Communication Foundation (WCF) tiene tres modos de seguridad comunes que se encuentran en la mayoría de los enlaces predefinidos: transporte, mensaje y "transporte con credenciales de mensaje".</span><span class="sxs-lookup"><span data-stu-id="3eba7-104">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="3eba7-105">Dos modos adicionales son específicos para dos enlaces: el modo “solo credencial de transporte” encontrado en el <xref:System.ServiceModel.BasicHttpBinding>y el modo “Ambos” encontrado en el <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="3eba7-105">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="3eba7-106">Sin embargo, este tema se concentra en los tres modos de seguridad comunes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>y <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="3eba7-106">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>

<span data-ttu-id="3eba7-107">Tenga en cuenta que no todos los enlaces predefinidos admiten todos estos modos.</span><span class="sxs-lookup"><span data-stu-id="3eba7-107">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="3eba7-108">Este tema establece el modo con las clases <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.NetTcpBinding> y muestra cómo establecer el modo mediante programación y configuración.</span><span class="sxs-lookup"><span data-stu-id="3eba7-108">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>

<span data-ttu-id="3eba7-109">Para obtener más información, vea seguridad de WCF, vea [información general sobre seguridad](./feature-details/security-overview.md), [proteger servicios](securing-services.md)y [proteger servicios y clientes](./feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="3eba7-109">For more information, see WCF security, see [Security Overview](./feature-details/security-overview.md), [Securing Services](securing-services.md), and [Securing Services and Clients](./feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="3eba7-110">Para obtener más información sobre el modo de transporte y el mensaje, vea [seguridad de transporte](./feature-details/transport-security.md) y [seguridad de mensajes](./feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="3eba7-110">For more information about transport mode and message, see [Transport Security](./feature-details/transport-security.md) and [Message Security](./feature-details/message-security-in-wcf.md).</span></span>

## <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="3eba7-111">Para establecer el modo de seguridad en código</span><span class="sxs-lookup"><span data-stu-id="3eba7-111">To set the security mode in code</span></span>

1. <span data-ttu-id="3eba7-112">Cree una instancia de la clase del enlace que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="3eba7-112">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="3eba7-113">Para obtener una lista de enlaces predefinidos, vea [enlaces proporcionados por el sistema](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="3eba7-113">For a list of predefined bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="3eba7-114">En el siguiente ejemplo se crea una instancia de la clase <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="3eba7-114">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

2. <span data-ttu-id="3eba7-115">Establezca la propiedad `Mode` del objeto devuelto por la propiedad `Security`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-115">Set the `Mode` property of the object returned by the `Security` property.</span></span>

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     <span data-ttu-id="3eba7-116">De manera alternativa, establezca el modo en mensaje, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba7-116">Alternatively, set the mode to message, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     <span data-ttu-id="3eba7-117">O establezca el modo en transporte con credenciales de mensaje, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba7-117">Or set the mode to transport with message credentials, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. <span data-ttu-id="3eba7-118">También puede establecer el modo en el constructor del enlace, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3eba7-118">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="3eba7-119">Establecimiento de la propiedad la propiedad ClientCredentialType </span><span class="sxs-lookup"><span data-stu-id="3eba7-119">Setting the ClientCredentialType Property</span></span>

<span data-ttu-id="3eba7-120">El establecimiento del modo en uno de los tres valores determina cómo establece la propiedad `ClientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-120">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="3eba7-121">Por ejemplo, el uso de la clase <xref:System.ServiceModel.WSHttpBinding>, estableciendo el modo en `Transport` implica que debe establecer la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.HttpTransportSecurity> en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="3eba7-121">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="3eba7-122">Para establecer la propiedad ClientCredentialType para el modo de transporte</span><span class="sxs-lookup"><span data-stu-id="3eba7-122">To set the ClientCredentialType property for Transport mode</span></span>

1. <span data-ttu-id="3eba7-123">Cree una instancia del enlace.</span><span class="sxs-lookup"><span data-stu-id="3eba7-123">Create an instance of the binding.</span></span>

2. <span data-ttu-id="3eba7-124">Establezca la propiedad `Mode` en `Transport`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-124">Set the `Mode` property to `Transport`.</span></span>

3. <span data-ttu-id="3eba7-125">Establezca la propiedad `ClientCredential` en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="3eba7-125">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="3eba7-126">El siguiente código establece la propiedad en `Windows`:</span><span class="sxs-lookup"><span data-stu-id="3eba7-126">The following code sets the property to `Windows`.</span></span>

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="3eba7-127">Para establecer la propiedad ClientCredentialType para el modo de mensaje</span><span class="sxs-lookup"><span data-stu-id="3eba7-127">To set the ClientCredentialType property for Message mode</span></span>

1. <span data-ttu-id="3eba7-128">Cree una instancia del enlace.</span><span class="sxs-lookup"><span data-stu-id="3eba7-128">Create an instance of the binding.</span></span>

2. <span data-ttu-id="3eba7-129">Establezca la propiedad `Mode` en `Message`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-129">Set the `Mode` property to `Message`.</span></span>

3. <span data-ttu-id="3eba7-130">Establezca la propiedad `ClientCredential` en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="3eba7-130">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="3eba7-131">El siguiente código establece la propiedad en `Certificate`:</span><span class="sxs-lookup"><span data-stu-id="3eba7-131">The following code sets the property to `Certificate`.</span></span>

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="3eba7-132">Para establecer el Modo y la propiedad ClientCredentialType en configuración</span><span class="sxs-lookup"><span data-stu-id="3eba7-132">To set the Mode and ClientCredentialType property in configuration</span></span>

1. <span data-ttu-id="3eba7-133">Agregue un elemento de enlace adecuado al [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3eba7-133">Add an appropriate binding element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="3eba7-134">En el siguiente ejemplo se agrega un [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3eba7-134">The following example adds a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

2. <span data-ttu-id="3eba7-135">Agregue un `<binding>` elemento y establezca su `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="3eba7-135">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="3eba7-136">Agregue un `<security>` elemento y establezca el `mode` atributo en `Message` , `Transport` o `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="3eba7-136">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

4. <span data-ttu-id="3eba7-137">Si se establece el modo en `Transport`, agregue un elemento `<transport>` en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="3eba7-137">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>

     <span data-ttu-id="3eba7-138">El siguiente ejemplo establece el modo en “`Transport"`, y, a continuación, establece el atributo `clientCredentialType` del `<transport>`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-138">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="3eba7-139">De manera alternativa, establezca el `security mode` en "`Message"`, seguido por un elemento `<"message">`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-139">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="3eba7-140">Este ejemplo establece el `clientCredentialType` en "`Certificate"`.</span><span class="sxs-lookup"><span data-stu-id="3eba7-140">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="3eba7-141">Utilizar el valor <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> es un caso especial y se explica más adelante.</span><span class="sxs-lookup"><span data-stu-id="3eba7-141">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>

### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="3eba7-142">Uso de TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3eba7-142">Using TransportWithMessageCredential</span></span>

<span data-ttu-id="3eba7-143">Al establecer el modo de seguridad en `TransportWithMessageCredential`, el transporte determina el mecanismo real que proporciona la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="3eba7-143">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="3eba7-144">Por ejemplo, el protocolo HTTP utiliza Secure Sockets Layer (SSL) sobre HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="3eba7-144">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="3eba7-145">Por consiguiente, se omite el establecimiento de la propiedad `ClientCredentialType` de cualquier objeto de seguridad de transporte (como <xref:System.ServiceModel.HttpTransportSecurity>).</span><span class="sxs-lookup"><span data-stu-id="3eba7-145">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="3eba7-146">En otras palabras, solo puede establecer el `ClientCredentialType` del objeto de seguridad del mensaje (para el enlace `WSHttpBinding`, el objeto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).</span><span class="sxs-lookup"><span data-stu-id="3eba7-146">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>

<span data-ttu-id="3eba7-147">Para obtener más información, consulte [Cómo: usar la seguridad de transporte y las credenciales de mensaje](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="3eba7-147">For more information, see [How to: Use Transport Security and Message Credentials](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3eba7-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eba7-148">See also</span></span>

- [<span data-ttu-id="3eba7-149">Procedimiento para configurar un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="3eba7-149">How to: Configure a Port with an SSL Certificate</span></span>](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="3eba7-150">Procedimiento para usar seguridad de transporte y credenciales de mensajes</span><span class="sxs-lookup"><span data-stu-id="3eba7-150">How to: Use Transport Security and Message Credentials</span></span>](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="3eba7-151">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="3eba7-151">Transport Security</span></span>](./feature-details/transport-security.md)
- [<span data-ttu-id="3eba7-152">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="3eba7-152">Message Security</span></span>](./feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="3eba7-153">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="3eba7-153">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="3eba7-154">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3eba7-154">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
