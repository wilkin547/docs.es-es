---
title: 'Cómo: Establecer el modo de seguridad'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
author: BrucePerlerMS
ms.openlocfilehash: 32fd1ebede841488d1bfabd2f92bd3fb1ffb55e8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193192"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="e05ef-102">Cómo: Establecer el modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="e05ef-102">How to: Set the Security Mode</span></span>
<span data-ttu-id="e05ef-103">Seguridad de Windows Communication Foundation (WCF) tiene tres modos de seguridad comunes que se encuentran en los enlaces más predefinidos: transporte, mensaje y "transporte con credencial de mensaje".</span><span class="sxs-lookup"><span data-stu-id="e05ef-103">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="e05ef-104">Dos modos adicionales son específicos para dos enlaces: el modo “solo credencial de transporte” encontrado en el <xref:System.ServiceModel.BasicHttpBinding>y el modo “Ambos” encontrado en el <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="e05ef-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="e05ef-105">Sin embargo, este tema se concentra en los tres modos de seguridad comunes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>y <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="e05ef-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
 <span data-ttu-id="e05ef-106">Tenga en cuenta que no todos los enlaces predefinidos admiten todos estos modos.</span><span class="sxs-lookup"><span data-stu-id="e05ef-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="e05ef-107">Este tema establece el modo con las clases <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.NetTcpBinding> y muestra cómo establecer el modo mediante programación y configuración.</span><span class="sxs-lookup"><span data-stu-id="e05ef-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>  
  
 <span data-ttu-id="e05ef-108">Para obtener más información, consulte seguridad WCF, vea [información general sobre seguridad](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), y [proteger servicios y clientes](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e05ef-108">For more information, see WCF security, see [Security Overview](../../../docs/framework/wcf/feature-details/security-overview.md), [Securing Services](../../../docs/framework/wcf/securing-services.md), and [Securing Services and Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="e05ef-109">Para obtener más información acerca del modo de transporte y mensaje, consulte [Transport Security](../../../docs/framework/wcf/feature-details/transport-security.md) y [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="e05ef-109">For more information about transport mode and message, see [Transport Security](../../../docs/framework/wcf/feature-details/transport-security.md) and [Message Security](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).</span></span>  
  
### <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="e05ef-110">Para establecer el modo de seguridad en código</span><span class="sxs-lookup"><span data-stu-id="e05ef-110">To set the security mode in code</span></span>  
  
1.  <span data-ttu-id="e05ef-111">Cree una instancia de la clase del enlace que está utilizando.</span><span class="sxs-lookup"><span data-stu-id="e05ef-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="e05ef-112">Para obtener una lista de enlaces predefinidos, vea [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="e05ef-112">For a list of predefined bindings, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="e05ef-113">En el siguiente ejemplo se crea una instancia de la clase <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e05ef-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
2.  <span data-ttu-id="e05ef-114">Establezca la propiedad `Mode` del objeto devuelto por la propiedad `Security`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     <span data-ttu-id="e05ef-115">De manera alternativa, establezca el modo en mensaje, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e05ef-115">Alternatively, set the mode to message, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     <span data-ttu-id="e05ef-116">O establezca el modo en transporte con credenciales de mensaje, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e05ef-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  <span data-ttu-id="e05ef-117">También puede establecer el modo en el constructor del enlace, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e05ef-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="e05ef-118">Establecimiento de la propiedad la propiedad ClientCredentialType </span><span class="sxs-lookup"><span data-stu-id="e05ef-118">Setting the ClientCredentialType Property</span></span>  
 <span data-ttu-id="e05ef-119">El establecimiento del modo en uno de los tres valores determina cómo establece la propiedad `ClientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="e05ef-120">Por ejemplo, el uso de la clase <xref:System.ServiceModel.WSHttpBinding>, estableciendo el modo en `Transport` implica que debe establecer la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.HttpTransportSecurity> en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="e05ef-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>  
  
#### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="e05ef-121">Para establecer la propiedad ClientCredentialType para el modo de transporte</span><span class="sxs-lookup"><span data-stu-id="e05ef-121">To set the ClientCredentialType property for Transport mode</span></span>  
  
1.  <span data-ttu-id="e05ef-122">Cree una instancia del enlace.</span><span class="sxs-lookup"><span data-stu-id="e05ef-122">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="e05ef-123">Establezca la propiedad `Mode` en `Transport`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-123">Set the `Mode` property to `Transport`.</span></span>  
  
3.  <span data-ttu-id="e05ef-124">Establezca la propiedad `ClientCredential` en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="e05ef-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="e05ef-125">El siguiente código establece la propiedad en `Windows`:</span><span class="sxs-lookup"><span data-stu-id="e05ef-125">The following code sets the property to `Windows`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="e05ef-126">Para establecer la propiedad ClientCredentialType para el modo de mensaje</span><span class="sxs-lookup"><span data-stu-id="e05ef-126">To set the ClientCredentialType property for Message mode</span></span>  
  
1.  <span data-ttu-id="e05ef-127">Cree una instancia del enlace.</span><span class="sxs-lookup"><span data-stu-id="e05ef-127">Create an instance of the binding.</span></span>  
  
2.  <span data-ttu-id="e05ef-128">Establezca la propiedad `Mode` en `Message`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-128">Set the `Mode` property to `Message`.</span></span>  
  
3.  <span data-ttu-id="e05ef-129">Establezca la propiedad `ClientCredential` en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="e05ef-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="e05ef-130">El siguiente código establece la propiedad en `Certificate`:</span><span class="sxs-lookup"><span data-stu-id="e05ef-130">The following code sets the property to `Certificate`.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="e05ef-131">Para establecer el Modo y la propiedad ClientCredentialType en configuración</span><span class="sxs-lookup"><span data-stu-id="e05ef-131">To set the Mode and ClientCredentialType property in configuration</span></span>  
  
1.  <span data-ttu-id="e05ef-132">Agregar un elemento de enlace apropiado para la [ \<enlaces >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e05ef-132">Add an appropriate binding element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="e05ef-133">En el ejemplo siguiente se agrega un [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e05ef-133">The following example adds a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
2.  <span data-ttu-id="e05ef-134">Agregar un `<binding>` y establezca su `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="e05ef-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="e05ef-135">Agregar un `<security>` y establezca el `mode` atributo `Message`, `Transport`, o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="e05ef-136">Si se establece el modo en `Transport`, agregue un elemento `<transport>` y establezca el atributo `clientCredential` en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="e05ef-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>  
  
     <span data-ttu-id="e05ef-137">El siguiente ejemplo establece el modo en "`Transport"`, y, a continuación, establece el atributo `clientCredentialType` del `<transport>`" en "`Windows"`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="e05ef-138">De manera alternativa, establezca el `security mode` en "`Message"`, seguido por un elemento `<"message">`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="e05ef-139">Este ejemplo establece el `clientCredentialType` en "`Certificate"`.</span><span class="sxs-lookup"><span data-stu-id="e05ef-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     <span data-ttu-id="e05ef-140">Utilizar el valor <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> es un caso especial y se explica más adelante.</span><span class="sxs-lookup"><span data-stu-id="e05ef-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>  
  
### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="e05ef-141">Uso de TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e05ef-141">Using TransportWithMessageCredential</span></span>  
 <span data-ttu-id="e05ef-142">Al establecer el modo de seguridad en `TransportWithMessageCredential`, el transporte determina el mecanismo real que proporciona la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="e05ef-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="e05ef-143">Por ejemplo, el protocolo HTTP utiliza Secure Sockets Layer (SSL) sobre HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="e05ef-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="e05ef-144">Por consiguiente, se omite el establecimiento de la propiedad `ClientCredentialType` de cualquier objeto de seguridad de transporte (como <xref:System.ServiceModel.HttpTransportSecurity>).</span><span class="sxs-lookup"><span data-stu-id="e05ef-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="e05ef-145">En otras palabras, solo puede establecer el `ClientCredentialType` del objeto de seguridad del mensaje (para el enlace `WSHttpBinding`, el objeto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).</span><span class="sxs-lookup"><span data-stu-id="e05ef-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>  
  
 <span data-ttu-id="e05ef-146">Para obtener más información, consulte [Cómo: usar la seguridad de transporte y credenciales de mensaje](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="e05ef-146">For more information, see [How to: Use Transport Security and Message Credentials](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05ef-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="e05ef-147">See Also</span></span>  
 [<span data-ttu-id="e05ef-148">Configuración de un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="e05ef-148">How to: Configure a Port with an SSL Certificate</span></span>](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [<span data-ttu-id="e05ef-149">Uso de la seguridad de transporte y las credenciales de mensajes</span><span class="sxs-lookup"><span data-stu-id="e05ef-149">How to: Use Transport Security and Message Credentials</span></span>](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)  
 [<span data-ttu-id="e05ef-150">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="e05ef-150">Transport Security</span></span>](../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="e05ef-151">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="e05ef-151">Message Security</span></span>](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 [<span data-ttu-id="e05ef-152">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="e05ef-152">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="e05ef-153">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e05ef-153">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="e05ef-154">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e05ef-154">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)  
 [<span data-ttu-id="e05ef-155">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e05ef-155">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)  
 [<span data-ttu-id="e05ef-156">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e05ef-156">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
