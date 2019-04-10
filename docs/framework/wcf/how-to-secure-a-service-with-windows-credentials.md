---
title: Filtrar para proteger un servicio con credenciales de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
ms.openlocfilehash: 5fb175bdd255af1b506dacb973a778b1f6f515f9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329354"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="f4c20-102">Filtrar para proteger un servicio con credenciales de Windows</span><span class="sxs-lookup"><span data-stu-id="f4c20-102">How to: Secure a Service with Windows Credentials</span></span>
<span data-ttu-id="f4c20-103">En este tema se muestra cómo habilitar la seguridad de transporte en un servicio de Windows Communication Foundation (WCF) que reside en un dominio de Windows y es llamado por los clientes en el mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-103">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="f4c20-104">Para obtener más información acerca de este escenario, consulte [seguridad de transporte con autenticación de Windows](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-104">For more information about this scenario, see [Transport Security with Windows Authentication](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="f4c20-105">Para una aplicación de ejemplo, consulte el [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4c20-105">For a sample application, see the [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  
  
 <span data-ttu-id="f4c20-106">En este tema se parte del supuesto de que ya tiene definidas una interfaz e implementación de contrato.</span><span class="sxs-lookup"><span data-stu-id="f4c20-106">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="f4c20-107">También puede modificar un servicio y cliente existentes.</span><span class="sxs-lookup"><span data-stu-id="f4c20-107">You can also modify an existing service and client.</span></span>  
  
 <span data-ttu-id="f4c20-108">Puede proteger completamente un servicio con credenciales de Windows en el código.</span><span class="sxs-lookup"><span data-stu-id="f4c20-108">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="f4c20-109">Alternativamente, puede omitir una parte del código mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f4c20-109">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="f4c20-110">En este tema se explican ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="f4c20-110">This topic shows both ways.</span></span> <span data-ttu-id="f4c20-111">Asegúrese de que sigue solamente uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="f4c20-111">Be sure you only use one of the ways, not both.</span></span>  
  
 <span data-ttu-id="f4c20-112">Los tres primeros procedimientos muestran cómo proteger el servicio en el código.</span><span class="sxs-lookup"><span data-stu-id="f4c20-112">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="f4c20-113">En el cuarto y quinto procedimientos se muestra cómo hacerlo con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f4c20-113">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>  
  
## <a name="using-code"></a><span data-ttu-id="f4c20-114">Mediante código</span><span class="sxs-lookup"><span data-stu-id="f4c20-114">Using Code</span></span>  
 <span data-ttu-id="f4c20-115">El código completo para el servicio y el cliente se encuentra en la sección Ejemplo al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f4c20-115">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>  
  
 <span data-ttu-id="f4c20-116">El primer procedimiento le guía en la creación y configuración de una clase <xref:System.ServiceModel.WSHttpBinding> en el código.</span><span class="sxs-lookup"><span data-stu-id="f4c20-116">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="f4c20-117">El enlace usa el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="f4c20-117">The binding uses the HTTP transport.</span></span> <span data-ttu-id="f4c20-118">El mismo enlace se usa en el cliente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-118">The same binding is used on the client.</span></span>  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="f4c20-119">Para crear un WSHttpBinding que utiliza credenciales de Windows y seguridad de mensaje</span><span class="sxs-lookup"><span data-stu-id="f4c20-119">To create a WSHttpBinding that uses Windows credentials and message security</span></span>  
  
1. <span data-ttu-id="f4c20-120">El código de este procedimiento se encuentra insertado al principio del método `Run` de la clase `Test` en el código del servicio, en la sección Ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4c20-120">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>  
  
2. <span data-ttu-id="f4c20-121">Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f4c20-121">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
3. <span data-ttu-id="f4c20-122">Establezca la propiedad <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> de la clase <xref:System.ServiceModel.WSHttpSecurity> en <xref:System.ServiceModel.SecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="f4c20-122">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
4. <span data-ttu-id="f4c20-123">Establezca la propiedad <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.MessageSecurityOverHttp> en <xref:System.ServiceModel.MessageCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="f4c20-123">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>  
  
5. <span data-ttu-id="f4c20-124">El código de este procedimiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4c20-124">The code for this procedure is as follows:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="f4c20-125">Utilizar el enlace en un servicio</span><span class="sxs-lookup"><span data-stu-id="f4c20-125">Using the Binding in a Service</span></span>  
 <span data-ttu-id="f4c20-126">Este es el segundo procedimiento, que muestra cómo usar el enlace en un servicio autohospedado.</span><span class="sxs-lookup"><span data-stu-id="f4c20-126">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="f4c20-127">Para obtener más información sobre el hospedaje de servicios vea [servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-127">For more information about hosting services see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="f4c20-128">Utilizar un enlace en un servicio</span><span class="sxs-lookup"><span data-stu-id="f4c20-128">To use a binding in a service</span></span>  
  
1. <span data-ttu-id="f4c20-129">Inserte el código de este procedimiento después del código del procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="f4c20-129">Insert this procedure's code after the code from the preceding procedure.</span></span>  
  
2. <span data-ttu-id="f4c20-130">Cree una variable <xref:System.Type>`contractType` con nombre y asígnele el tipo de la interfaz (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="f4c20-130">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="f4c20-131">Al usar Visual Basic, utilice el `GetType` operador; cuando se usa C#, utilice el `typeof` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f4c20-131">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>  
  
3. <span data-ttu-id="f4c20-132">Cree una segunda variable <xref:System.Type>`serviceType` con nombre y asígnele el tipo del contrato implementado (`Calculator`).</span><span class="sxs-lookup"><span data-stu-id="f4c20-132">Create a second <xref:System.Type> variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>  
  
4. <span data-ttu-id="f4c20-133">Cree una instancia de la clase <xref:System.Uri> denominada `baseAddress` con la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-133">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="f4c20-134">La dirección base debe tener un esquema que coincida con el transporte.</span><span class="sxs-lookup"><span data-stu-id="f4c20-134">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="f4c20-135">En este caso, el esquema de transporte es HTTP y la dirección incluye especial "Localhost" de identificador uniforme de recursos (URI) y un puerto de número (8036), así como una dirección de punto de conexión base ("serviceModelSamples /): `http://localhost:8036/serviceModelSamples/`.</span><span class="sxs-lookup"><span data-stu-id="f4c20-135">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): `http://localhost:8036/serviceModelSamples/`.</span></span>  
  
5. <span data-ttu-id="f4c20-136">Cree una instancia de la clase<xref:System.ServiceModel.ServiceHost> con `serviceType` y variables `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="f4c20-136">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>  
  
6. <span data-ttu-id="f4c20-137">Agregue un punto de conexión al servicio incluyendo `contractType`, el enlace y el nombre del punto de conexión ("secureCalculator").</span><span class="sxs-lookup"><span data-stu-id="f4c20-137">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="f4c20-138">Un cliente debe concatenar la dirección base y el nombre de punto de conexión al iniciar una llamada al servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-138">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>  
  
7. <span data-ttu-id="f4c20-139">Llame al método <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-139">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="f4c20-140">El código de este procedimiento se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="f4c20-140">The code for this procedure is shown here:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="f4c20-141">Utilizar el enlace en un cliente</span><span class="sxs-lookup"><span data-stu-id="f4c20-141">Using the Binding in a Client</span></span>  
 <span data-ttu-id="f4c20-142">Este procedimiento muestra cómo generar un proxy que se comunica con el servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-142">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="f4c20-143">El proxy se genera con el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) que usa los metadatos del servicio para crear el proxy.</span><span class="sxs-lookup"><span data-stu-id="f4c20-143">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>  
  
 <span data-ttu-id="f4c20-144">En este procedimiento también se crea una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> para comunicarse con el servicio y, a continuación, se llama al servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-144">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>  
  
 <span data-ttu-id="f4c20-145">Este ejemplo solo utiliza código para crear el cliente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-145">This example uses only code to create the client.</span></span> <span data-ttu-id="f4c20-146">Como alternativa, puede utilizar un archivo de configuración, que se muestra en la sección que sigue a este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f4c20-146">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="f4c20-147">Para usar un enlace en un cliente con el código</span><span class="sxs-lookup"><span data-stu-id="f4c20-147">To use a binding in a client with code</span></span>  
  
1. <span data-ttu-id="f4c20-148">Use la herramienta SvcUtil.exe para generar el código del proxy a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-148">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="f4c20-149">Para obtener más información, vea [Cómo: Crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-149">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="f4c20-150">El código proxy generado hereda la <xref:System.ServiceModel.ClientBase%601> (clase), lo que garantiza que cada cliente tiene los constructores necesarios, métodos y propiedades para comunicarse con un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f4c20-150">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="f4c20-151">En este ejemplo, el código generado incluye la clase `CalculatorClient`, que implementa la interfaz `ICalculator`, habilitando la compatibilidad con el código del servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-151">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>  
  
2. <span data-ttu-id="f4c20-152">El código de este procedimiento se encuentra insertado al principio del método `Main` del programa cliente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-152">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
3. <span data-ttu-id="f4c20-153">Cree una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y establezca su modo de seguridad en `Message` y su tipo de credencial de cliente en `Windows`.</span><span class="sxs-lookup"><span data-stu-id="f4c20-153">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="f4c20-154">El ejemplo denomina el `clientBinding`variable.</span><span class="sxs-lookup"><span data-stu-id="f4c20-154">The example names the variable `clientBinding`.</span></span>  
  
4. <span data-ttu-id="f4c20-155">Cree una instancia de la clase <xref:System.ServiceModel.EndpointAddress> denominada `serviceAddress`.</span><span class="sxs-lookup"><span data-stu-id="f4c20-155">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="f4c20-156">Inicialice la instancia con la dirección base concatenada con el nombre de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f4c20-156">Initialize the instance with the base address concatenated with the endpoint name.</span></span>  
  
5. <span data-ttu-id="f4c20-157">Cree una instancia de la clase de cliente generada con `serviceAddress` y las variables `clientBinding`.</span><span class="sxs-lookup"><span data-stu-id="f4c20-157">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>  
  
6. <span data-ttu-id="f4c20-158">Llame al método <xref:System.ServiceModel.ClientBase%601.Open%2A>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="f4c20-158">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
7. <span data-ttu-id="f4c20-159">Llame al servicio y muestre los resultados.</span><span class="sxs-lookup"><span data-stu-id="f4c20-159">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a><span data-ttu-id="f4c20-160">Usar el archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f4c20-160">Using the Configuration File</span></span>  
 <span data-ttu-id="f4c20-161">En lugar de crear el enlace con código de procedimiento, puede usar el código siguiente, que se muestra para la sección de enlaces del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f4c20-161">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>  
  
 <span data-ttu-id="f4c20-162">Si no dispone de un servicio definido, consulte [diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md), y [configurar Services](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-162">If you do not already have a service defined, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md), and [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
 <span data-ttu-id="f4c20-163">**Tenga en cuenta** este código de configuración se utiliza en los archivos de configuración del servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-163">**Note** This configuration code is used in both the service and client configuration files.</span></span>  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="f4c20-164">Habilitar la seguridad de la transferencia en un servicio en un dominio de Windows utilizando la configuración</span><span class="sxs-lookup"><span data-stu-id="f4c20-164">To enable transfer security on a service in a Windows domain using configuration</span></span>  
  
1. <span data-ttu-id="f4c20-165">Agregar un [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento a la [ \<enlaces >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sección del elemento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f4c20-165">Add a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>  
  
2. <span data-ttu-id="f4c20-166">Agregar un <`binding`> elemento para el <`WSHttpBinding`> y establezca el `configurationName` en un valor apropiado para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4c20-166">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>  
  
3. <span data-ttu-id="f4c20-167">Agregar un <`security`> y establezca el `mode` atributo al mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4c20-167">Add a <`security`> element and set the `mode` attribute to Message.</span></span>  
  
4. <span data-ttu-id="f4c20-168">Agregar un <`message`> y establezca el `clientCredentialType` atribuir a Windows.</span><span class="sxs-lookup"><span data-stu-id="f4c20-168">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>  
  
5. <span data-ttu-id="f4c20-169">En el archivo de configuración del servicio, reemplace la sección `<bindings>` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-169">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="f4c20-170">Si no dispone de un archivo de configuración de servicio, consulte [uso de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-170">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="f4c20-171">Utilizar el enlace en un cliente</span><span class="sxs-lookup"><span data-stu-id="f4c20-171">Using the Binding in a Client</span></span>  
 <span data-ttu-id="f4c20-172">En este procedimiento se muestra cómo generar dos archivos: un proxy que se comunica con el servicio y un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f4c20-172">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="f4c20-173">También se describen los cambios en el programa cliente, que es el tercer archivo utilizado en el cliente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-173">It also describes changes to the client program, which is the third file used on the client.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="f4c20-174">Para usar un enlace en un cliente mediante configuración</span><span class="sxs-lookup"><span data-stu-id="f4c20-174">To use a binding in a client with configuration</span></span>  
  
1. <span data-ttu-id="f4c20-175">Use la herramienta SvcUtil.exe para generar el código proxy y el archivo de configuración a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="f4c20-175">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="f4c20-176">Para obtener más información, vea [Cómo: Crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-176">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="f4c20-177">Reemplace el [ \<enlaces >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) sección del archivo de configuración generado con el código de configuración de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="f4c20-177">Replace the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>  
  
3. <span data-ttu-id="f4c20-178">El código de procedimiento se encuentra insertado al principio del método `Main` del programa cliente.</span><span class="sxs-lookup"><span data-stu-id="f4c20-178">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
4. <span data-ttu-id="f4c20-179">Cree una instancia de la clase de cliente generada, pasando el nombre del enlace en el archivo de configuración como parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="f4c20-179">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>  
  
5. <span data-ttu-id="f4c20-180">Llame al método <xref:System.ServiceModel.ClientBase%601.Open%2A>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="f4c20-180">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
6. <span data-ttu-id="f4c20-181">Llame al servicio y muestre los resultados.</span><span class="sxs-lookup"><span data-stu-id="f4c20-181">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="f4c20-182">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4c20-182">Example</span></span>  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)] 
 [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]      
  
## <a name="see-also"></a><span data-ttu-id="f4c20-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4c20-183">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- [<span data-ttu-id="f4c20-184">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f4c20-184">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="f4c20-185">Filtrar Crear un cliente</span><span class="sxs-lookup"><span data-stu-id="f4c20-185">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="f4c20-186">Seguridad de servicios</span><span class="sxs-lookup"><span data-stu-id="f4c20-186">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="f4c20-187">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="f4c20-187">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
