---
title: Procedimiento para especificar un enlace de servicio en la configuración
description: Obtenga información sobre cómo configurar un punto de conexión para un servicio WCF en un archivo de configuración. Se define un contrato para un servicio y se implementa en una clase.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 3b9dd12f2a28ae2d420e82013459613cee8140f1
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051953"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="95a56-104">Procedimiento para especificar un enlace de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="95a56-104">How to: Specify a Service Binding in Configuration</span></span>
<span data-ttu-id="95a56-105">En este ejemplo, se define un contrato `ICalculator` para un servicio de calculadora básico; el servicio se implementa en la clase `CalculatorService` y, después, su punto de conexión se configura en el archivo Web.config, donde se especifica que el servicio usa <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="95a56-105">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="95a56-106">Para obtener una descripción de cómo configurar este servicio con código en lugar de una configuración, vea [Cómo: especificar un enlace de servicio en el código](how-to-specify-a-service-binding-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="95a56-106">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="95a56-107">Normalmente es el mejor procedimiento para especificar el enlace y la información de dirección de forma declarativa en configuración en lugar de hacerlo de forma imperativa en código.</span><span class="sxs-lookup"><span data-stu-id="95a56-107">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="95a56-108">Normalmente, no resulta muy práctico definir los puntos de conexión en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio.</span><span class="sxs-lookup"><span data-stu-id="95a56-108">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="95a56-109">Más generalmente, manteniendo el enlace y la información de dirección fuera del código permite cambiarlos sin tener que recompilar o implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95a56-109">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="95a56-110">Todos los pasos de configuración siguientes se pueden llevar a cabo mediante la [herramienta editor de configuración (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="95a56-110">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="95a56-111">Para la copia de origen de este ejemplo, consulte [BasicBinding](./samples/basicbinding.md).</span><span class="sxs-lookup"><span data-stu-id="95a56-111">For the source copy of this example, see [BasicBinding](./samples/basicbinding.md).</span></span>  
  
## <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="95a56-112">Para especificar BasicHttpBinding para utilizarlo para configurar el servicio</span><span class="sxs-lookup"><span data-stu-id="95a56-112">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1. <span data-ttu-id="95a56-113">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="95a56-113">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="95a56-114">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="95a56-114">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="95a56-115">La información de dirección o enlace no se especifica dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="95a56-115">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="95a56-116">Por lo tanto, el código no tiene que escribirse para recuperar esa información del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="95a56-116">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3. <span data-ttu-id="95a56-117">Cree un archivo Web.config para configurar un punto de conexión para `CalculatorService` que utiliza <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="95a56-117">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  

            <!-- Leave the address blank to be populated by default -->
            <!-- from the hosting environment,in this case IIS, so -->
            <!-- the address will just be that of the IIS Virtual -->
            <!-- Directory. -->

            <!-- Specify the binding configuration name for that -->
            <!-- binding type. This is optional but useful if you -->
            <!-- want to modify the properties of the binding. -->
            <!-- The bindingConfiguration name Binding1 is defined -->
            <!-- below in the bindings element. -->
            <endpoint
                address=""
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="95a56-118">Cree un archivo Service.svc que contenga la línea siguiente y colóquelo en su directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="95a56-118">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```aspx-csharp
    <%@ServiceHost language=c# Service="CalculatorService" %>
    ```  
  
## <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="95a56-119">Para modificar los valores predeterminados de las propiedades de enlace</span><span class="sxs-lookup"><span data-stu-id="95a56-119">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="95a56-120">Para modificar uno de los valores de propiedad predeterminados de <xref:System.ServiceModel.WSHttpBinding> , cree un nuevo nombre de configuración de enlace, `<binding name="Binding1">` en el [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento y establezca los nuevos valores para los atributos del enlace en este elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="95a56-120">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="95a56-121">Por ejemplo, para cambiar los valores predeterminados de abrir y cerrar el tiempo de espera de 1 minuto a 2 minutos, agregue el siguiente al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="95a56-121">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="95a56-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="95a56-122">See also</span></span>

- [<span data-ttu-id="95a56-123">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="95a56-123">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="95a56-124">Especificación de una dirección de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="95a56-124">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
