---
description: 'Más información sobre: procedimientos recomendados: intermediarios'
title: 'Procedimientos recomendados: intermediarios'
ms.date: 03/30/2017
ms.assetid: 2d41b337-8132-4ac2-bea2-6e9ae2f00f8d
ms.openlocfilehash: 54fd367c9dd7a3b40f585d095d51042acd8b5722
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430500"
---
# <a name="best-practices-intermediaries"></a><span data-ttu-id="988f7-103">Procedimientos recomendados: intermediarios</span><span class="sxs-lookup"><span data-stu-id="988f7-103">Best Practices: Intermediaries</span></span>

<span data-ttu-id="988f7-104">Se debe tener cuidado para controlar los errores correctamente al llamar a intermediarios para asegurarse de que los canales en el lado servicio se han cerrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="988f7-104">Care must be taken to handle faults correctly when calling intermediaries to make sure service side channels on the intermediary are closed properly.</span></span>  
  
 <span data-ttu-id="988f7-105">Considere el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="988f7-105">Consider the following scenario.</span></span> <span data-ttu-id="988f7-106">Un cliente realiza una llamada a un intermedio que llama a un servicio de back-end.</span><span class="sxs-lookup"><span data-stu-id="988f7-106">A client makes a call to an intermediary which then calls a back-end service.</span></span>  <span data-ttu-id="988f7-107">El servicio back-end no define ningún contrato de error, de modo que cualquier error de ese servicio se tratará como un error no tipado.</span><span class="sxs-lookup"><span data-stu-id="988f7-107">The back-end service defines no fault contract, so any fault thrown from that service will be treated as an un-typed fault.</span></span>  <span data-ttu-id="988f7-108">El servicio back-end inicia una <xref:System.ApplicationException> y WCF anula correctamente el canal del lado del servicio.</span><span class="sxs-lookup"><span data-stu-id="988f7-108">The back-end service throws an <xref:System.ApplicationException> and WCF correctly aborts the service-side channel.</span></span> <span data-ttu-id="988f7-109"><xref:System.ApplicationException> emerge como <xref:System.ServiceModel.FaultException> que se inicia en el intermediario.</span><span class="sxs-lookup"><span data-stu-id="988f7-109">The <xref:System.ApplicationException> then surfaces as a <xref:System.ServiceModel.FaultException> that is thrown to the intermediary.</span></span> <span data-ttu-id="988f7-110">El intermediario vuelve a iniciar <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="988f7-110">The intermediary re-throws the <xref:System.ApplicationException>.</span></span> <span data-ttu-id="988f7-111">WCF interpreta esto como un error no tipado del intermediario y se lo reenvía al cliente.</span><span class="sxs-lookup"><span data-stu-id="988f7-111">WCF interprets this as an un-typed fault from the intermediary and forwards it on to the client.</span></span> <span data-ttu-id="988f7-112">Al recibir el error, el intermediario y el cliente generan errores en los canales de lado de cliente.</span><span class="sxs-lookup"><span data-stu-id="988f7-112">Upon receiving the fault, both the intermediary and the client fault their client-side channels.</span></span> <span data-ttu-id="988f7-113">Sin embargo, el canal del lado de servicio del intermediario permanece abierto porque WCF no sabe que el error es irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="988f7-113">The intermediary’s service-side channel however remains open because WCF doesn’t know the fault is fatal.</span></span>  
  
 <span data-ttu-id="988f7-114">La recomendación en este escenario es detectar si el error que procede del servicio es irrecuperable y, en tal caso, el intermediario debería producir un error en su canal de lado de servicio como se muestra en el fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="988f7-114">The best practice in this scenario is to detect if the fault coming from the service is fatal and if so the intermediary should fault its service-side channel as shown in the following code snippet.</span></span>  
  
```csharp  
catch (Exception e)  
{  
    bool faulted = service.State == CommunicationState.Faulted;  
    service.Abort();  
    if (faulted)  
    {  
        throw new ApplicationException(e.Message);  
    }  
    else  
    {  
        throw;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="988f7-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="988f7-115">See also</span></span>

- [<span data-ttu-id="988f7-116">Control de errores de WCF</span><span class="sxs-lookup"><span data-stu-id="988f7-116">WCF Error Handling</span></span>](wcf-error-handling.md)
- [<span data-ttu-id="988f7-117">Especificación y administración de errores en contratos y servicios</span><span class="sxs-lookup"><span data-stu-id="988f7-117">Specifying and Handling Faults in Contracts and Services</span></span>](specifying-and-handling-faults-in-contracts-and-services.md)
