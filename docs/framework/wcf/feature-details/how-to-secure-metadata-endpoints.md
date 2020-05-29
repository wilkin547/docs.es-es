---
title: Procedimiento para proteger puntos de conexión de metadatos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
ms.openlocfilehash: 2746c608fb47b94446c5d7e10748ba185d555e7f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202327"
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="98d41-102">Procedimiento para proteger puntos de conexión de metadatos</span><span class="sxs-lookup"><span data-stu-id="98d41-102">How to: Secure Metadata Endpoints</span></span>

<span data-ttu-id="98d41-103">Los metadatos para un servicio pueden contener información confidencial sobre su aplicación que un usuario malintencionado puede aprovechar.</span><span class="sxs-lookup"><span data-stu-id="98d41-103">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="98d41-104">Los consumidores de su servicio también pueden requerir un mecanismo seguro para obtener los metadatos sobre su servicio.</span><span class="sxs-lookup"><span data-stu-id="98d41-104">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="98d41-105">Por consiguiente, a veces es necesario publicar sus metadatos utilizando un extremo seguro.</span><span class="sxs-lookup"><span data-stu-id="98d41-105">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>

<span data-ttu-id="98d41-106">Los puntos de conexión de metadatos generalmente se protegen utilizando los mecanismos de seguridad estándar definidos en Windows Communication Foundation (WCF) para proteger los puntos de conexión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98d41-106">Metadata endpoints are generally secured using the standard security mechanisms defined in Windows Communication Foundation (WCF) for securing application endpoints.</span></span> <span data-ttu-id="98d41-107">Para más información, consulte [Introducción a la seguridad](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98d41-107">For more information, see [Security Overview](security-overview.md).</span></span>

<span data-ttu-id="98d41-108">En este tema se describen los pasos para crear un extremo protegido por un certificado SSL (Capa de sockets seguros) o, en otras palabras, un extremo de HTTPS.</span><span class="sxs-lookup"><span data-stu-id="98d41-108">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="98d41-109">Para crear un extremo seguro de metadatos HTTPS GET en código</span><span class="sxs-lookup"><span data-stu-id="98d41-109">To create a secure HTTPS GET metadata endpoint in code</span></span>

1. <span data-ttu-id="98d41-110">Configure un puerto con un certificado X.509 adecuado.</span><span class="sxs-lookup"><span data-stu-id="98d41-110">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="98d41-111">El certificado debe proceder de una autoridad de confianza y debe tener un uso previsto de "Autorización de servicio."</span><span class="sxs-lookup"><span data-stu-id="98d41-111">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="98d41-112">Debe utilizar la herramienta HttpCfg.exe para asociar el certificado al puerto.</span><span class="sxs-lookup"><span data-stu-id="98d41-112">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="98d41-113">Consulte [Cómo: configurar un puerto con un certificado SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="98d41-113">See [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="98d41-114">El asunto del certificado o su Domain Name System (DNS) debe coincidir con el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="98d41-114">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="98d41-115">Esto es esencial porque uno de los primeros pasos que el mecanismo de HTTPS realiza es comprobar que el certificado esté emitido para el mismo identificador URI (Uniform Resource Identifier) que la dirección en la que se invoca.</span><span class="sxs-lookup"><span data-stu-id="98d41-115">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>

2. <span data-ttu-id="98d41-116">Cree una nueva instancia de la clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="98d41-116">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>

3. <span data-ttu-id="98d41-117">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> de la clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en `true`.</span><span class="sxs-lookup"><span data-stu-id="98d41-117">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>

4. <span data-ttu-id="98d41-118">Establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> en una URL adecuada.</span><span class="sxs-lookup"><span data-stu-id="98d41-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="98d41-119">Tenga en cuenta que si especifica una dirección absoluta, la dirección URL debe comenzar con el esquema `https://` .</span><span class="sxs-lookup"><span data-stu-id="98d41-119">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="98d41-120">Si especifica una dirección relativa, debe proporcionar una dirección base de HTTPS para su host de servicio.</span><span class="sxs-lookup"><span data-stu-id="98d41-120">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="98d41-121">Si esta propiedad no está establecida, la dirección predeterminada es "", o directamente en la dirección base de HTTPS para el servicio.</span><span class="sxs-lookup"><span data-stu-id="98d41-121">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

5. <span data-ttu-id="98d41-122">Agregue la instancia a la colección de comportamientos que la propiedad <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> de las clases <xref:System.ServiceModel.Description.ServiceDescription> devuelve, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="98d41-122">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>

    [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
    [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="98d41-123">Para crear un punto de conexión seguro de metadatos HTTPS GET en configuración</span><span class="sxs-lookup"><span data-stu-id="98d41-123">To create a secure HTTPS GET metadata endpoint in configuration</span></span>

1. <span data-ttu-id="98d41-124">Agregue un [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento al [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento del archivo de configuración para el servicio.</span><span class="sxs-lookup"><span data-stu-id="98d41-124">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>

2. <span data-ttu-id="98d41-125">Agregue un [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) elemento al [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="98d41-125">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

3. <span data-ttu-id="98d41-126">Agregue un [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento al `<serviceBehaviors>` elemento.</span><span class="sxs-lookup"><span data-stu-id="98d41-126">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>

4. <span data-ttu-id="98d41-127">Establezca el atributo `name` del elemento `<behavior>` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="98d41-127">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="98d41-128">El atributo `name` es necesario.</span><span class="sxs-lookup"><span data-stu-id="98d41-128">The `name` attribute is required.</span></span> <span data-ttu-id="98d41-129">El ejemplo siguiente utiliza el valor `mySvcBehavior`.</span><span class="sxs-lookup"><span data-stu-id="98d41-129">The example below uses the value `mySvcBehavior`.</span></span>

5. <span data-ttu-id="98d41-130">Agregue un [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) al `<behavior>` elemento.</span><span class="sxs-lookup"><span data-stu-id="98d41-130">Add a [\<serviceMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>

6. <span data-ttu-id="98d41-131">Establezca el atributo `httpsGetEnabled` del elemento `<serviceMetadata>` en `true`:</span><span class="sxs-lookup"><span data-stu-id="98d41-131">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>

7. <span data-ttu-id="98d41-132">Establezca el atributo `httpsGetUrl` del elemento `<serviceMetadata>` en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="98d41-132">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="98d41-133">Tenga en cuenta que si especifica una dirección absoluta, la dirección URL debe comenzar con el esquema `https://` .</span><span class="sxs-lookup"><span data-stu-id="98d41-133">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="98d41-134">Si especifica una dirección relativa, debe proporcionar una dirección base de HTTPS para su host de servicio.</span><span class="sxs-lookup"><span data-stu-id="98d41-134">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="98d41-135">Si esta propiedad no está establecida, la dirección predeterminada es "", o directamente en la dirección base de HTTPS para el servicio.</span><span class="sxs-lookup"><span data-stu-id="98d41-135">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

8. <span data-ttu-id="98d41-136">Para utilizar el comportamiento con un servicio, establezca el `behaviorConfiguration` atributo del [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) elemento en el valor del atributo name del elemento Behavior.</span><span class="sxs-lookup"><span data-stu-id="98d41-136">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="98d41-137">El código de configuración siguiente muestra un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="98d41-137">The following configuration code shows a complete example.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
     <system.serviceModel>
      <behaviors>
       <serviceBehaviors>
        <behavior name="mySvcBehavior">
         <serviceMetadata httpsGetEnabled="true"
              httpsGetUrl="https://localhost:8036/calcMetadata" />
        </behavior>
       </serviceBehaviors>
      </behaviors>
     <services>
      <service behaviorConfiguration="mySvcBehavior"
            name="Microsoft.Security.Samples.Calculator">
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"
       binding="wsHttpBinding" bindingConfiguration=""
       contract="Microsoft.Security.Samples.ICalculator" />
      </service>
     </services>
    </system.serviceModel>
    </configuration>
    ```

## <a name="example"></a><span data-ttu-id="98d41-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98d41-138">Example</span></span>

<span data-ttu-id="98d41-139">El ejemplo siguiente crea una instancia de una clase <xref:System.ServiceModel.ServiceHost> y agrega un extremo.</span><span class="sxs-lookup"><span data-stu-id="98d41-139">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="98d41-140">El código crea a continuación una instancia de la clase <xref:System.ServiceModel.Description.ServiceMetadataBehavior> y establece las propiedades para crear un punto de intercambio seguro de metadatos.</span><span class="sxs-lookup"><span data-stu-id="98d41-140">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>

[!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
[!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="98d41-141">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="98d41-141">Compiling the Code</span></span>

<span data-ttu-id="98d41-142">El ejemplo de código utiliza los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="98d41-142">The code example uses the following namespaces:</span></span>

- <xref:System.ServiceModel?displayProperty=nameWithType>

- <xref:System.ServiceModel.Description?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="98d41-143">Consulta también</span><span class="sxs-lookup"><span data-stu-id="98d41-143">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="98d41-144">Procedimiento para configurar un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="98d41-144">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="98d41-145">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="98d41-145">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="98d41-146">Consideraciones de seguridad con metadatos</span><span class="sxs-lookup"><span data-stu-id="98d41-146">Security Considerations with Metadata</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)
- [<span data-ttu-id="98d41-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="98d41-147">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
