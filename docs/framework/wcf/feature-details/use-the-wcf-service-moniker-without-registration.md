---
description: 'Más información acerca de cómo: usar el moniker del servicio Windows Communication Foundation sin registro'
title: Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: ed3ea221bc32c4334f609b6740fa10bb63cb2830
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632391"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="5a1ef-103">Procedimiento para usar el moniker de servicio de Windows Communication Foundation sin registrarse</span><span class="sxs-lookup"><span data-stu-id="5a1ef-103">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>

<span data-ttu-id="5a1ef-104">Para conectarse y comunicarse con un servicio de Windows Communication Foundation (WCF), una aplicación cliente de WCF debe tener los detalles de la dirección del servicio, la configuración del enlace y el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-104">To connect to and communicate with a Windows Communication Foundation (WCF) service, a WCF client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="5a1ef-105">Normalmente, el moniker de servicio de WCF obtiene el contrato necesario a través del registro anterior de los tipos de atributo necesarios, pero puede haber casos en los que esto no sea factible.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-105">The WCF service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="5a1ef-106">En lugar del registro, el moniker puede obtener la definición del contrato en forma de documento de lenguaje de descripción de servicios Web (WSDL), mediante el uso del parámetro `wsdl` o a través de Metadatos Exchange, utilizando el parámetro `mexAddress`.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-106">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="5a1ef-107">Esto habilita escenarios como la distribución de una hoja de cálculo de Excel en la que algunos de los valores de celda se calculan mediante las interacciones del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-107">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="5a1ef-108">En este escenario, puede no ser posible registrar el ensamblado de contrato de servicios en todos los clientes que podrían abrir el documento.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-108">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="5a1ef-109">El parámetro `wsdl` o el parámetro `mexAddress` habilitan una solución autónoma.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-109">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a1ef-110">La autenticación mutua debe utilizarse como protección frente a la manipulación o suplantación de solicitudes o respuestas.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-110">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="5a1ef-111">Más concretamente, es importante para los clientes estar seguros de que el punto de conexión del intercambio de metadatos es la parte de confianza interesada.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-111">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1ef-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a1ef-112">Example</span></span>  

 <span data-ttu-id="5a1ef-113">Este ejemplo muestra el uso del moniker de servicio con un contrato MEX (Metadata Exchange).</span><span class="sxs-lookup"><span data-stu-id="5a1ef-113">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="5a1ef-114">Un servicio con el siguiente contrato se expone con wsHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-114">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
```csharp
using System.ServiceModel;  
  
// ...
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 <span data-ttu-id="5a1ef-115">Para construir un cliente WCF para el servicio remoto, se puede usar la cadena de moniker de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-115">To construct a WCF client for the remote service the following example moniker string can be used.</span></span>  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="5a1ef-116">Durante la ejecución de la aplicación cliente, el cliente realiza `WS-MetadataExchange` con la `mexAddress` proporcionada.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-116">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="5a1ef-117">Esto podría devolver los detalles de la dirección, el enlace y el contrato de varios servicios.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-117">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="5a1ef-118">Los parámetros `address`, `contract`, `contractNamespace`, `binding` y `bindingNamespace` se utilizan para identificar el servicio deseado.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-118">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="5a1ef-119">Una vez que se han encontrado los parámetros, el moniker crea un cliente de WCF con la definición de contrato adecuada y, a continuación, se puede realizar llamadas mediante el cliente WCF, como con el contrato con tipo.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-119">Once those parameters have been matched, the moniker constructs a WCF client with the appropriate contract definition and calls can then be made using the WCF client, as with the typed contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a1ef-120">Si el moniker es incorrecto o el servicio no está disponible, la llamada a `GetObject` devuelve un error informando de que la sintaxis no es válida.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-120">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="5a1ef-121">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="5a1ef-121">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1ef-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a1ef-122">See also</span></span>

- [<span data-ttu-id="5a1ef-123">Procedimiento para registrar y configurar un moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="5a1ef-123">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)
