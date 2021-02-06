---
description: 'Más información acerca de: uso de contratos en el flujo de trabajo'
title: Utilizar contratos en flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
ms.openlocfilehash: d1ef5a4c494643d521a5fe045ff87c0cbeb34db1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632222"
---
# <a name="using-contracts-in-workflow"></a><span data-ttu-id="0d644-103">Utilizar contratos en flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0d644-103">Using Contracts in Workflow</span></span>

<span data-ttu-id="0d644-104">Al implementar un servicio, defina varios contratos que describan el servicio y los datos que envía y recibe.</span><span class="sxs-lookup"><span data-stu-id="0d644-104">When implementing a service, you define a number of contracts that describe the service and the data that it sends and receives.</span></span> <span data-ttu-id="0d644-105">Los datos se representan como contratos de datos y contratos de mensajes; tanto WCF como los servicios de flujo de trabajo usan las definiciones de contrato de datos y contrato de datos como parte de las descripciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="0d644-105">The data is represented as data contracts and message contracts; both WCF and workflow services use data contract and message contract definitions as part of service descriptions.</span></span> <span data-ttu-id="0d644-106">El servicio expone metadatos (en el formulario de WSDL) para describir las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="0d644-106">The service itself exposes metadata (in the form of WSDL) in order to describe the operations of the service.</span></span> <span data-ttu-id="0d644-107">En WCF, los contratos de servicios y los contratos de operaciones definen el servicio y las operaciones admitidos.</span><span class="sxs-lookup"><span data-stu-id="0d644-107">In WCF, service contracts and operation contracts define the service and the operations it supports.</span></span> <span data-ttu-id="0d644-108">Sin embargo, en un servicio de flujo de trabajo, estos contratos forman parte del propio proceso de negocio; se exponen en metadatos mediante un proceso llamado inferencia del contrato.</span><span class="sxs-lookup"><span data-stu-id="0d644-108">However, in a workflow service, these contracts are part of the business process itself; they are exposed in metadata by a process called contract inference.</span></span>  
  
## <a name="contract-inference"></a><span data-ttu-id="0d644-109">Inferencia del contrato</span><span class="sxs-lookup"><span data-stu-id="0d644-109">Contract Inference</span></span>  

 <span data-ttu-id="0d644-110">Cuando un servicio de flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se examina la definición de flujo de trabajo y se genera un contrato en función del conjunto de actividades de mensajería presentes en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0d644-110">When a workflow service is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, the workflow definition is examined and a contract is generated based on the set of messaging activities found in the workflow.</span></span> <span data-ttu-id="0d644-111">En especial, se emplean las siguientes actividades y propiedades para generar el contrato:</span><span class="sxs-lookup"><span data-stu-id="0d644-111">In particular the following activities and properties are used to generate the contract:</span></span>  
  
 <span data-ttu-id="0d644-112"><xref:System.ServiceModel.Activities.Receive> Actividad</span><span class="sxs-lookup"><span data-stu-id="0d644-112"><xref:System.ServiceModel.Activities.Receive> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
- <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
- <xref:System.ServiceModel.Activities.Receive.Action%2A>

 <span data-ttu-id="0d644-113"><xref:System.ServiceModel.Activities.SendReply> Actividad</span><span class="sxs-lookup"><span data-stu-id="0d644-113"><xref:System.ServiceModel.Activities.SendReply> Activity</span></span>  
  
- <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <span data-ttu-id="0d644-114"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Actividad</span><span class="sxs-lookup"><span data-stu-id="0d644-114"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Activity</span></span>  
  
 <span data-ttu-id="0d644-115">El resultado final de inferencia del contrato es una descripción del servicio mediante las mismas estructuras de datos que el servicio de WCF y los contratos de operación.</span><span class="sxs-lookup"><span data-stu-id="0d644-115">The end result of contract inference is a description of the service using the same data structures as WCF service and operation contracts.</span></span> <span data-ttu-id="0d644-116">A continuación, esta información se utiliza para exponer WSDL para el servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0d644-116">This information is then used to expose WSDL for the workflow service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d644-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d644-117">See also</span></span>

- [<span data-ttu-id="0d644-118">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0d644-118">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="0d644-119">Actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="0d644-119">Messaging Activities</span></span>](messaging-activities.md)
- [<span data-ttu-id="0d644-120">Procedimiento para crear un servicio de flujo de trabajo con actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="0d644-120">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)
- [<span data-ttu-id="0d644-121">Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="0d644-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
