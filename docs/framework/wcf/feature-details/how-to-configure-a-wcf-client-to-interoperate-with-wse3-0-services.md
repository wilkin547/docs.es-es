---
title: Procedimiento para configurar un cliente WCF para interoperar con los servicios WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 7dd50fcc07c6c090042cf87acb4aa5d2b5321a68
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579584"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="d2ae3-102">Procedimiento para configurar un cliente WCF para interoperar con los servicios WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d2ae3-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="d2ae3-103">Los clientes de Windows Communication Foundation (WCF) son compatibles en el nivel de conexión con las mejoras de servicios web 3,0 para los servicios de Microsoft .NET (WSE) cuando los clientes de WCF están configurados para usar la versión de agosto de 2004 de la especificación WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="d2ae3-104">Configuración de un cliente WCF para interoperar con un servicio web WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="d2ae3-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1. <span data-ttu-id="d2ae3-105">Ejecute la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un cliente WCF para el servicio Web WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="d2ae3-106">Para un servicio Web de WSE, se crea una clase de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="d2ae3-107">Para obtener más información acerca de cómo crear un cliente de WCF, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="d2ae3-107">For details about creating a WCF client, see the [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="d2ae3-108">Cree una clase que represente un enlace que puede comunicarse con los servicios Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="d2ae3-109">La clase siguiente forma parte del ejemplo de [interoperabilidad con WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) .</span><span class="sxs-lookup"><span data-stu-id="d2ae3-109">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample.</span></span>  
  
    1. <span data-ttu-id="d2ae3-110">Cree una clase que se derive de la clase <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="d2ae3-111">En el siguiente ejemplo de código se crea una clase denominada `WseHttpBinding`, que se deriva de la clase <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="d2ae3-112">Agregue propiedades a la clase que especifiquen la aserción de llave en mano WSE, si se requieren las claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="d2ae3-113">En el ejemplo de código siguiente se definen las `SecurityAssertion` `RequireDerivedKeys` propiedades,, `EstablishSecurityContext` y `MessageProtectionOrder` .</span><span class="sxs-lookup"><span data-stu-id="d2ae3-113">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="d2ae3-114">Especifican la aserción de llave en mano de WSE, si se requieren claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-114">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="d2ae3-115">Anule el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> para definir las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-115">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="d2ae3-116">El ejemplo de código siguiente especifica el transporte, codificación de mensajes y configuración de protección de mensajes obteniendo los valores de las propiedades `SecurityAssertion` y `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-116">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="d2ae3-117">En el código de la aplicación cliente, agregue el código para definir las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-117">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="d2ae3-118">En el ejemplo de código siguiente se especifica que el cliente de WCF debe usar la protección de mensajes y la autenticación tal y como se define en la aserción de seguridad inmediata de WSE 3,0 `AnonymousForCertificate` .</span><span class="sxs-lookup"><span data-stu-id="d2ae3-118">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="d2ae3-119">Además, se requieren sesiones seguras y claves derivadas.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-119">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="d2ae3-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2ae3-120">Example</span></span>  
 <span data-ttu-id="d2ae3-121">El ejemplo de código siguiente define un enlace personalizado que expone propiedades que corresponden a las propiedades de una aserción de seguridad de llave en mano WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-121">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="d2ae3-122">El enlace personalizado, que se denomina `WseHttpBinding` , se utiliza para especificar las propiedades de enlace de un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="d2ae3-122">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="d2ae3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2ae3-123">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- [<span data-ttu-id="d2ae3-124">Interoperarabilidad con WSE</span><span class="sxs-lookup"><span data-stu-id="d2ae3-124">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
