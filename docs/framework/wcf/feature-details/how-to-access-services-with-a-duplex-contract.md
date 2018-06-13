---
title: 'Cómo: Obtener acceso a los servicios con un contrato dúplex'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: c0022e6ce3a63c1f497eeee82ca959cec1046cec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490157"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="f3491-102">Cómo: Obtener acceso a los servicios con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="f3491-102">How to: Access Services with a Duplex Contract</span></span>
<span data-ttu-id="f3491-103">Una característica de Windows Communication Foundation (WCF) es la capacidad para crear un servicio que utiliza un patrón de mensajería dúplex.</span><span class="sxs-lookup"><span data-stu-id="f3491-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="f3491-104">Este patrón permite a un servicio comunicarse con el cliente mediante una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f3491-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="f3491-105">En este tema se muestra los pasos para crear a un cliente WCF en una clase de cliente que implementa la interfaz de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f3491-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>  
  
 <span data-ttu-id="f3491-106">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="f3491-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="f3491-107">El cliente debería utilizar la seguridad para asegurarse de que solo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3491-107">The client should use security to ensure that it connects only to services it trusts.</span></span>  
  
 <span data-ttu-id="f3491-108">Para obtener un tutorial sobre cómo crear un servicio WCF básico y un cliente, consulte [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="f3491-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
### <a name="to-access-a-duplex-service"></a><span data-ttu-id="f3491-109">Obtención de acceso a un servicio dúplex</span><span class="sxs-lookup"><span data-stu-id="f3491-109">To access a duplex service</span></span>  
  
1.  <span data-ttu-id="f3491-110">Cree un servicio que contenga dos interfaces.</span><span class="sxs-lookup"><span data-stu-id="f3491-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="f3491-111">La primera interfaz es para el servicio, la segunda es para la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f3491-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="f3491-112">Para obtener más información acerca de cómo crear un servicio dúplex, consulte [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f3491-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
2.  <span data-ttu-id="f3491-113">Ejecute el servicio.</span><span class="sxs-lookup"><span data-stu-id="f3491-113">Run the service.</span></span>  
  
3.  <span data-ttu-id="f3491-114">Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar contratos (interfaces) para el cliente.</span><span class="sxs-lookup"><span data-stu-id="f3491-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="f3491-115">Para obtener información acerca de cómo hacerlo, consulte [Cómo: crear un cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="f3491-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
4.  <span data-ttu-id="f3491-116">Implemente la interfaz de devolución de llamada en la clase de cliente, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f3491-116">Implement the callback interface in the client class, as shown in the following example.</span></span>  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  <span data-ttu-id="f3491-117">Cree una instancia de la clase <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="f3491-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="f3491-118">El constructor necesita una instancia de la clase cliente.</span><span class="sxs-lookup"><span data-stu-id="f3491-118">The constructor requires an instance of the client class.</span></span>  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  <span data-ttu-id="f3491-119">Cree una instancia del cliente WCF mediante el constructor que requiere un <xref:System.ServiceModel.InstanceContext> objeto.</span><span class="sxs-lookup"><span data-stu-id="f3491-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="f3491-120">El segundo parámetro del constructor es el nombre de un punto de conexión encontrado en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f3491-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  <span data-ttu-id="f3491-121">Llamar a los métodos del cliente WCF según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f3491-121">Call the methods of the WCF client as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3491-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3491-122">Example</span></span>  
 <span data-ttu-id="f3491-123">El siguiente ejemplo de código muestra cómo crear una clase de cliente que tenga acceso a un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="f3491-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="f3491-124">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3491-124">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3491-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3491-125">See Also</span></span>  
 [<span data-ttu-id="f3491-126">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="f3491-126">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="f3491-127">Creación de un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="f3491-127">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="f3491-128">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f3491-128">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="f3491-129">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="f3491-129">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="f3491-130">Uso de ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f3491-130">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
