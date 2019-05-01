---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039681"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="4a588-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="4a588-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="4a588-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="4a588-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a588-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a588-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4a588-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4a588-105">Methods</span></span>  
 <span data-ttu-id="4a588-106">La clase DeliveryRequirementsAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="4a588-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4a588-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4a588-107">Properties</span></span>  
 <span data-ttu-id="4a588-108">La clase DeliveryRequirementsAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a588-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="4a588-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="4a588-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="4a588-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4a588-110">Data type: string</span></span>  
  
 <span data-ttu-id="4a588-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="4a588-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a588-112">Especifica si el enlace para un servicio admite contratos.</span><span class="sxs-lookup"><span data-stu-id="4a588-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="4a588-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="4a588-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="4a588-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4a588-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4a588-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="4a588-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a588-116">Especifica si el enlace admite mensajes ordenados.</span><span class="sxs-lookup"><span data-stu-id="4a588-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="4a588-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="4a588-117">TargetContract</span></span>  
 <span data-ttu-id="4a588-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4a588-118">Data type: string</span></span>  
  
 <span data-ttu-id="4a588-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="4a588-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a588-120">El contrato al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="4a588-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a588-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a588-121">Requirements</span></span>  
  
|<span data-ttu-id="4a588-122">MOF</span><span class="sxs-lookup"><span data-stu-id="4a588-122">MOF</span></span>|<span data-ttu-id="4a588-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4a588-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4a588-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4a588-124">Namespace</span></span>|<span data-ttu-id="4a588-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4a588-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a588-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a588-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
