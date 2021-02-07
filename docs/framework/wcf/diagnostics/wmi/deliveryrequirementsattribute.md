---
description: 'Más información acerca de: DeliveryRequirementsAttribute'
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: ee27ada1c1fb447de3d7a108a4a285ca106e4e8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757506"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="e9d54-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="e9d54-103">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="e9d54-104">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="e9d54-104">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9d54-105">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e9d54-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="e9d54-106">Methods</span></span>  

 <span data-ttu-id="e9d54-107">La clase DeliveryRequirementsAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e9d54-107">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e9d54-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e9d54-108">Properties</span></span>  

 <span data-ttu-id="e9d54-109">La clase DeliveryRequirementsAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9d54-109">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="e9d54-110">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="e9d54-110">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="e9d54-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e9d54-111">Data type: string</span></span>  
  
 <span data-ttu-id="e9d54-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e9d54-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9d54-113">Especifica si el enlace para un servicio admite contratos.</span><span class="sxs-lookup"><span data-stu-id="e9d54-113">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="e9d54-114">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="e9d54-114">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="e9d54-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e9d54-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="e9d54-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e9d54-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9d54-117">Especifica si el enlace admite mensajes ordenados.</span><span class="sxs-lookup"><span data-stu-id="e9d54-117">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="e9d54-118">TargetContract</span><span class="sxs-lookup"><span data-stu-id="e9d54-118">TargetContract</span></span>  

 <span data-ttu-id="e9d54-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e9d54-119">Data type: string</span></span>  
  
 <span data-ttu-id="e9d54-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e9d54-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9d54-121">El contrato al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="e9d54-121">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d54-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9d54-122">Requirements</span></span>  
  
|<span data-ttu-id="e9d54-123">MOF</span><span class="sxs-lookup"><span data-stu-id="e9d54-123">MOF</span></span>|<span data-ttu-id="e9d54-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e9d54-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e9d54-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e9d54-125">Namespace</span></span>|<span data-ttu-id="e9d54-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e9d54-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9d54-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9d54-127">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
