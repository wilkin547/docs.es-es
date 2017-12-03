---
title: "Cómo: Especificar los valores de credenciales de cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42c6390fb2bd39a0003beecbbe10cd72a38ed63d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="c17dc-102">Cómo: Especificar los valores de credenciales de cliente</span><span class="sxs-lookup"><span data-stu-id="c17dc-102">How to: Specify Client Credential Values</span></span>
<span data-ttu-id="c17dc-103">Con [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], el servicio puede especificar cómo se debe autenticar un cliente con él.</span><span class="sxs-lookup"><span data-stu-id="c17dc-103">Using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="c17dc-104">Por ejemplo, un servicio puede estipular que el cliente se autentique mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="c17dc-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>  
  
### <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="c17dc-105">Para determinar el tipo de credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="c17dc-105">To determine the client credential type</span></span>  
  
1.  <span data-ttu-id="c17dc-106">Recupere los metadatos del extremo de metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="c17dc-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="c17dc-107">Normalmente, los metadatos constan de dos archivos: el código de cliente en el lenguaje de programación elegido (el predeterminado es Visual C#), y un archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="c17dc-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="c17dc-108">Una manera de recuperar los metadatos consiste en usar la herramienta Svcutil.exe para devolver el código y la configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="c17dc-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="c17dc-109">Para obtener más información, consulte [recuperación de metadatos](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) y [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c17dc-109">For more information, see [Retrieving Metadata](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
2.  <span data-ttu-id="c17dc-110">Abra el archivo de configuración XML.</span><span class="sxs-lookup"><span data-stu-id="c17dc-110">Open the XML configuration file.</span></span> <span data-ttu-id="c17dc-111">Si usa la herramienta Svcutil.exe, el nombre predeterminado del archivo es Output.config.</span><span class="sxs-lookup"><span data-stu-id="c17dc-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>  
  
3.  <span data-ttu-id="c17dc-112">Buscar el  **\<seguridad >** elemento con la **modo** atributo (**< SecurityMode =** `MessageOrTransport`  **>**  donde `MessageOrTransport` se establece en uno de los modos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c17dc-112">Find the **\<security>** element with the **mode** attribute (**<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>  
  
4.  <span data-ttu-id="c17dc-113">Busque el elemento secundario que coincida con el valor del modo.</span><span class="sxs-lookup"><span data-stu-id="c17dc-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="c17dc-114">Por ejemplo, si el modo está establecido en **mensaje**, buscar el  **\<mensaje >** los elementos en el  **\<seguridad >** elemento.</span><span class="sxs-lookup"><span data-stu-id="c17dc-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>  
  
5.  <span data-ttu-id="c17dc-115">Tenga en cuenta el valor asignado a la **clientCredentialType** atributo.</span><span class="sxs-lookup"><span data-stu-id="c17dc-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="c17dc-116">El valor real dependerá del modo que se use, de transporte o de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c17dc-116">The actual value depends on which mode is used, transport or message.</span></span>  
  
 <span data-ttu-id="c17dc-117">El código XML siguiente muestra la configuración de un cliente usando la seguridad de mensajes y solicitando un certificado para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="c17dc-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="c17dc-118">Ejemplo: modo de transporte TCP con certificado como credencial de cliente</span><span class="sxs-lookup"><span data-stu-id="c17dc-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>  
 <span data-ttu-id="c17dc-119">Este ejemplo establece el modo de seguridad en transporte y establece el valor de credencial de cliente en un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="c17dc-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="c17dc-120">Los procedimientos siguientes muestran cómo establecer el valor de credencial de cliente en el cliente en código y configuración.</span><span class="sxs-lookup"><span data-stu-id="c17dc-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="c17dc-121">Se supone que ha usado el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para devolver los metadatos (código y configuración) desde el servicio.</span><span class="sxs-lookup"><span data-stu-id="c17dc-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="c17dc-122">[Cómo: crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="c17dc-122"> [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="c17dc-123">Para especificar el valor de credencial de cliente en el cliente en código</span><span class="sxs-lookup"><span data-stu-id="c17dc-123">To specify the client credential value on the client in code</span></span>  
  
1.  <span data-ttu-id="c17dc-124">Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar código y la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="c17dc-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>  
  
2.  <span data-ttu-id="c17dc-125">Cree una instancia del cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] utilizando el código generado.</span><span class="sxs-lookup"><span data-stu-id="c17dc-125">Create an instance of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client using the generated code.</span></span>  
  
3.  <span data-ttu-id="c17dc-126">En la clase de cliente, establezca la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> de la clase <xref:System.ServiceModel.ClientBase%601> en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="c17dc-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="c17dc-127">Este ejemplo establece la propiedad en un certificado X.509 utilizando el método <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="c17dc-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <span data-ttu-id="c17dc-128">Puede utilizar cualquiera de las enumeraciones de la clase <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="c17dc-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="c17dc-129">El nombre de sujeto se utiliza aquí en caso de que se cambie el certificado (debido a una fecha de caducidad).</span><span class="sxs-lookup"><span data-stu-id="c17dc-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="c17dc-130">Utilizar el nombre de sujeto permite a la infraestructura encontrar de nuevo el certificado.</span><span class="sxs-lookup"><span data-stu-id="c17dc-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="c17dc-131">Para especificar el valor de credencial de cliente en el cliente en configuración</span><span class="sxs-lookup"><span data-stu-id="c17dc-131">To specify the client credential value on the client in configuration</span></span>  
  
1.  <span data-ttu-id="c17dc-132">Agregar un [ \<comportamiento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento a la [ \<comportamientos >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c17dc-132">Add a [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
2.  <span data-ttu-id="c17dc-133">Agregar un [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento a la [ \<comportamientos >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c17dc-133">Add a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="c17dc-134">Asegúrese de establecer el atributo `name` necesario en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="c17dc-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="c17dc-135">Agregar un [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elemento a la [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c17dc-135">Add a [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
4.  <span data-ttu-id="c17dc-136">Establezca los atributos siguientes en los valores adecuados: `storeLocation`, `storeName`, `x509FindType` y `findValue`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c17dc-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c17dc-137">certificados, consulte [trabajar con certificados](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c17dc-137"> certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  <span data-ttu-id="c17dc-138">Al configurar el cliente, especifique el comportamiento estableciendo el atributo `behaviorConfiguration` del elemento `<endpoint>`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c17dc-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="c17dc-139">El punto de conexión es un elemento secundario de la [ \<cliente >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="c17dc-139">The endpoint element is a child of the [\<client>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="c17dc-140">Especifique también el nombre de la configuración de enlace estableciendo el atributo `bindingConfiguration` en el enlace para el cliente.</span><span class="sxs-lookup"><span data-stu-id="c17dc-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="c17dc-141">Si está utilizando un archivo de configuración generado, se genera automáticamente el nombre del enlace.</span><span class="sxs-lookup"><span data-stu-id="c17dc-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="c17dc-142">En este ejemplo, el nombre es `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="c17dc-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c17dc-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="c17dc-143">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="c17dc-144">Programar la seguridad WCF</span><span class="sxs-lookup"><span data-stu-id="c17dc-144">Programming WCF Security</span></span>](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [<span data-ttu-id="c17dc-145">Al seleccionar un tipo de credencial</span><span class="sxs-lookup"><span data-stu-id="c17dc-145">Selecting a Credential Type</span></span>](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="c17dc-146">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="c17dc-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="c17dc-147">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="c17dc-147">Working with Certificates</span></span>](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="c17dc-148">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="c17dc-148">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="c17dc-149">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="c17dc-149">\<netTcpBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [<span data-ttu-id="c17dc-150">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="c17dc-150">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [<span data-ttu-id="c17dc-151">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="c17dc-151">\<message></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [<span data-ttu-id="c17dc-152">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c17dc-152">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [<span data-ttu-id="c17dc-153">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c17dc-153">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [<span data-ttu-id="c17dc-154">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="c17dc-154">\<clientCertificate></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [<span data-ttu-id="c17dc-155">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="c17dc-155">\<clientCredentials></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
