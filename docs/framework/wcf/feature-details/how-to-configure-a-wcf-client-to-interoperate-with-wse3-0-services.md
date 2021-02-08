---
description: Más información acerca de cómo configurar un cliente WCF para interoperar con los servicios WSE 3.0
title: Procedimiento para configurar un cliente WCF para interoperar con los servicios WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 97de90c491a29cdacf881a92013a11db6aea416f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780133"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="bed55-103">Procedimiento para configurar un cliente WCF para interoperar con los servicios WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="bed55-103">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>

<span data-ttu-id="bed55-104">Los clientes de Windows Communication Foundation (WCF) son compatibles en el nivel de conexión con las mejoras de servicios web 3,0 para los servicios de Microsoft .NET (WSE) cuando los clientes de WCF están configurados para usar la versión de agosto de 2004 de la especificación de WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="bed55-104">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="bed55-105">Configuración de un cliente WCF para interoperar con un servicio web WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="bed55-105">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1. <span data-ttu-id="bed55-106">Ejecute la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para crear un cliente WCF para el servicio Web WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="bed55-106">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="bed55-107">Para un servicio Web de WSE, se crea una clase de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="bed55-107">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="bed55-108">Para obtener más información acerca de cómo crear un cliente de WCF, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="bed55-108">For details about creating a WCF client, see the [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="bed55-109">Cree una clase que represente un enlace que puede comunicarse con los servicios Web WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="bed55-109">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="bed55-110">La clase siguiente forma parte del ejemplo de [interoperabilidad con WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) .</span><span class="sxs-lookup"><span data-stu-id="bed55-110">The following class is part of the [Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) sample.</span></span>  
  
    1. <span data-ttu-id="bed55-111">Cree una clase que se derive de la clase <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="bed55-111">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="bed55-112">En el siguiente ejemplo de código se crea una clase denominada `WseHttpBinding`, que se deriva de la clase <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="bed55-112">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="bed55-113">Agregue propiedades a la clase que especifiquen la aserción de llave en mano WSE, si se requieren las claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes.</span><span class="sxs-lookup"><span data-stu-id="bed55-113">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="bed55-114">En el ejemplo de código siguiente se definen las `SecurityAssertion` `RequireDerivedKeys` propiedades,, `EstablishSecurityContext` y `MessageProtectionOrder` .</span><span class="sxs-lookup"><span data-stu-id="bed55-114">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="bed55-115">Especifican la aserción de llave en mano de WSE, si se requieren claves derivadas, si se utilizan sesiones seguras, si se requieren confirmaciones de firmas, y la configuración de protección de mensajes, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="bed55-115">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="bed55-116">Anule el método <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> para definir las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="bed55-116">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="bed55-117">El ejemplo de código siguiente especifica el transporte, codificación de mensajes y configuración de protección de mensajes obteniendo los valores de las propiedades `SecurityAssertion` y `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="bed55-117">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="bed55-118">En el código de la aplicación cliente, agregue el código para definir las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="bed55-118">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="bed55-119">En el ejemplo de código siguiente se especifica que el cliente de WCF debe usar la protección de mensajes y la autenticación tal y como se define en la aserción de seguridad inmediata de WSE 3,0 `AnonymousForCertificate` .</span><span class="sxs-lookup"><span data-stu-id="bed55-119">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="bed55-120">Además, se requieren sesiones seguras y claves derivadas.</span><span class="sxs-lookup"><span data-stu-id="bed55-120">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="bed55-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bed55-121">Example</span></span>  

 <span data-ttu-id="bed55-122">El ejemplo de código siguiente define un enlace personalizado que expone propiedades que corresponden a las propiedades de una aserción de seguridad de llave en mano WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="bed55-122">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="bed55-123">El enlace personalizado, que se denomina `WseHttpBinding` , se utiliza para especificar las propiedades de enlace de un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="bed55-123">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="bed55-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="bed55-124">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <span data-ttu-id="bed55-125">[Interoperarabilidad con WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="bed55-125">[Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))</span></span>
