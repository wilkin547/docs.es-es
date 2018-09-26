---
title: Cómo utilizar seguridad de transporte y credenciales de mensajes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
author: BrucePerlerMS
ms.openlocfilehash: 40fe7b1fa6a61b56d5dfdde75a92834f096a8be4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200417"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="f045f-102">Cómo utilizar seguridad de transporte y credenciales de mensajes</span><span class="sxs-lookup"><span data-stu-id="f045f-102">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="f045f-103">Protección de un servicio con credenciales de mensajes y transporte usa lo mejor de los modos de seguridad de mensajes y transporte en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f045f-103">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f045f-104">En suma, la seguridad de la capa de transporte proporciona integridad y confidencialidad, mientras que la seguridad de la capa de mensaje proporciona una variedad de credenciales que no son posibles con mecanismos de seguridad de transporte estrictos.</span><span class="sxs-lookup"><span data-stu-id="f045f-104">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="f045f-105">En este tema se muestran los pasos básicos para implementar transporte con credenciales de mensaje usando los enlaces <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f045f-105">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="f045f-106">Para obtener más información acerca de cómo establecer el modo de seguridad, consulte [Cómo: establecer el modo de seguridad](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f045f-106">For more information about setting the security mode, see [How to: Set the Security Mode](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="f045f-107">Al establecer el modo de seguridad en `TransportWithMessageCredential`, el transporte determina el mecanismo real que proporciona la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="f045f-107">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="f045f-108">Para HTTP, el mecanismo es Secure Sockets Layer (SSL) sobre HTTP (HTTPS); para TCP, es SSL sobre TCP o Windows.</span><span class="sxs-lookup"><span data-stu-id="f045f-108">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="f045f-109">Si el transporte es HTTP (utilizando <xref:System.ServiceModel.WSHttpBinding>), SSL sobre HTTP proporciona la seguridad de nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="f045f-109">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="f045f-110">En ese caso, debe configurar el equipo que aloja el servicio con un certificado SSL enlazado a un puerto, tal y como se muestra más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f045f-110">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="f045f-111">Si el transporte es TCP (utilizando <xref:System.ServiceModel.NetTcpBinding>), la seguridad de nivel de transporte proporcionada es, de forma predeterminada, seguridad de Windows, o SSL sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="f045f-111">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="f045f-112">Al utilizar SSL sobre TCP, debe especificar el certificado mediante el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>, tal y como se muestra más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f045f-112">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="f045f-113">Para utilizar WSHttpBinding con un certificado para la seguridad de transporte (en código)</span><span class="sxs-lookup"><span data-stu-id="f045f-113">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="f045f-114">Utilice la herramienta HttpCfg.exe para enlazar un certificado SSL a un puerto en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f045f-114">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="f045f-115">Para obtener más información, consulte [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="f045f-115">For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2.  <span data-ttu-id="f045f-116">Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> en <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="f045f-116">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3.  <span data-ttu-id="f045f-117">Establezca la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="f045f-117">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="f045f-118">(Para obtener más información, consulte [seleccionar un tipo de credencial](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) El siguiente código usa el valor <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="f045f-118">(For more information, see [Selecting a Credential Type](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4.  <span data-ttu-id="f045f-119">Cree una instancia de la clase <xref:System.Uri> con una dirección base apropiada.</span><span class="sxs-lookup"><span data-stu-id="f045f-119">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="f045f-120">Observe que la dirección debe utilizar el esquema "HTTPS" y contener el nombre real del equipo y el número de puerto al que se enlaza el certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="f045f-120">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="f045f-121">(De manera alternativa, puede establecer la dirección base mediante configuración.)</span><span class="sxs-lookup"><span data-stu-id="f045f-121">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5.  <span data-ttu-id="f045f-122">Agregue un extremo de servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="f045f-122">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6.  <span data-ttu-id="f045f-123">Cree la instancia del <xref:System.ServiceModel.ServiceHost> y llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f045f-123">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="f045f-124">Para usar el NetTcpBinding con un certificado para la seguridad de transporte (en código)</span><span class="sxs-lookup"><span data-stu-id="f045f-124">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="f045f-125">Cree una instancia de la clase <xref:System.ServiceModel.NetTcpBinding> y establezca la propiedad <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> en <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="f045f-125">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2.  <span data-ttu-id="f045f-126">Establezca un valor adecuado para la propiedad <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f045f-126">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="f045f-127">El siguiente código usa el valor <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="f045f-127">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3.  <span data-ttu-id="f045f-128">Cree una instancia de la clase <xref:System.Uri> con una dirección base apropiada.</span><span class="sxs-lookup"><span data-stu-id="f045f-128">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="f045f-129">Observe que la dirección debe utilizar el esquema "net.tcp."</span><span class="sxs-lookup"><span data-stu-id="f045f-129">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="f045f-130">(De manera alternativa, puede establecer la dirección base mediante configuración.)</span><span class="sxs-lookup"><span data-stu-id="f045f-130">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4.  <span data-ttu-id="f045f-131">Cree la instancia de la clase <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f045f-131">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5.  <span data-ttu-id="f045f-132">Utilice el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para establecer explícitamente el certificado X.509 para el servicio.</span><span class="sxs-lookup"><span data-stu-id="f045f-132">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6.  <span data-ttu-id="f045f-133">Agregue un extremo de servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="f045f-133">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7.  <span data-ttu-id="f045f-134">Llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="f045f-134">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="f045f-135">Para utilizar NetTcpBinding con Windows para la seguridad de transporte (en código)</span><span class="sxs-lookup"><span data-stu-id="f045f-135">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="f045f-136">Cree una instancia de la clase <xref:System.ServiceModel.NetTcpBinding> y establezca la propiedad <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> en <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="f045f-136">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2.  <span data-ttu-id="f045f-137">Establezca la seguridad de transporte para que utilice Windows estableciendo el <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> como <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="f045f-137">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="f045f-138">(Observe que se trata del valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f045f-138">(Note that this is the default.)</span></span>  
  
3.  <span data-ttu-id="f045f-139">Establezca un valor adecuado para la propiedad <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f045f-139">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="f045f-140">El siguiente código usa el valor <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="f045f-140">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4.  <span data-ttu-id="f045f-141">Cree una instancia de la clase <xref:System.Uri> con una dirección base apropiada.</span><span class="sxs-lookup"><span data-stu-id="f045f-141">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="f045f-142">Observe que la dirección debe utilizar el esquema "net.tcp."</span><span class="sxs-lookup"><span data-stu-id="f045f-142">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="f045f-143">(De manera alternativa, puede establecer la dirección base mediante configuración.)</span><span class="sxs-lookup"><span data-stu-id="f045f-143">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5.  <span data-ttu-id="f045f-144">Cree la instancia de la clase <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="f045f-144">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6.  <span data-ttu-id="f045f-145">Utilice el método <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> para establecer explícitamente el certificado X.509 para el servicio.</span><span class="sxs-lookup"><span data-stu-id="f045f-145">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7.  <span data-ttu-id="f045f-146">Agregue un extremo de servicio mediante el método <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="f045f-146">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8.  <span data-ttu-id="f045f-147">Llame al método <xref:System.ServiceModel.ICommunicationObject.Open%2A>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="f045f-147">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="f045f-148">Uso de la configuración</span><span class="sxs-lookup"><span data-stu-id="f045f-148">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="f045f-149">Para usar el WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f045f-149">To use the WSHttpBinding</span></span>  
  
1.  <span data-ttu-id="f045f-150">Configure el equipo con un certificado SSL enlazado a un puerto.</span><span class="sxs-lookup"><span data-stu-id="f045f-150">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="f045f-151">(Para obtener más información, consulte [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="f045f-151">(For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="f045f-152">No es necesario establecer una <`transport`> valor del elemento con esta configuración.</span><span class="sxs-lookup"><span data-stu-id="f045f-152">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2.  <span data-ttu-id="f045f-153">Especifique el tipo de credencial de cliente para la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="f045f-153">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="f045f-154">El ejemplo siguiente se establece la `clientCredentialType` atributo de la <`message`> elemento para `UserName`.</span><span class="sxs-lookup"><span data-stu-id="f045f-154">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="f045f-155">Para usar el NetTcpBinding con un certificado para la seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="f045f-155">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1.  <span data-ttu-id="f045f-156">Para SSL sobre TCP, debe especificar explícitamente el certificado en el elemento `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="f045f-156">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="f045f-157">El siguiente ejemplo especifica un certificado por su emisor en la ubicación de almacén predeterminada (equipo local y almacenes personales).</span><span class="sxs-lookup"><span data-stu-id="f045f-157">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  <span data-ttu-id="f045f-158">Agregar un [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) a la sección de enlaces</span><span class="sxs-lookup"><span data-stu-id="f045f-158">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3.  <span data-ttu-id="f045f-159">Agregue un elemento de enlace y establezca un valor apropiado para el atributo `name`.</span><span class="sxs-lookup"><span data-stu-id="f045f-159">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="f045f-160">Agregar un <`security`> y establezca el `mode` atributo `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="f045f-160">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5.  <span data-ttu-id="f045f-161">Agregar un <`message>` y establezca el `clientCredentialType` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f045f-161">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="f045f-162">Para utilizar NetTcpBinding con Windows para la seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="f045f-162">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1.  <span data-ttu-id="f045f-163">Agregar un [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) a la sección de enlaces</span><span class="sxs-lookup"><span data-stu-id="f045f-163">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2.  <span data-ttu-id="f045f-164">Agregar un <`binding`> y establezca el `name` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f045f-164">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="f045f-165">Agregar un <`security`> y establezca el `mode` atributo `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="f045f-165">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="f045f-166">Agregar un <`transport`> y establezca el `clientCredentialType` atributo `Windows`.</span><span class="sxs-lookup"><span data-stu-id="f045f-166">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5.  <span data-ttu-id="f045f-167">Agregar un <`message`> y establezca el `clientCredentialType` atributo en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="f045f-167">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="f045f-168">El siguiente código establece el valor para un certificado.</span><span class="sxs-lookup"><span data-stu-id="f045f-168">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f045f-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="f045f-169">See Also</span></span>  
 [<span data-ttu-id="f045f-170">Cómo establecer el modo de seguridad</span><span class="sxs-lookup"><span data-stu-id="f045f-170">How to: Set the Security Mode</span></span>](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)  
 [<span data-ttu-id="f045f-171">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="f045f-171">Securing Services</span></span>](../../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="f045f-172">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f045f-172">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
