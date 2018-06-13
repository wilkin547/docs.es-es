---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: d294ba4f14472012b9e311ee53742633b5173f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485834"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="10dd3-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="10dd3-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="10dd3-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="10dd3-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10dd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10dd3-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="10dd3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="10dd3-105">Methods</span></span>  
 <span data-ttu-id="10dd3-106">La clase DeliveryRequirementsAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="10dd3-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="10dd3-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="10dd3-107">Properties</span></span>  
 <span data-ttu-id="10dd3-108">La clase DeliveryRequirementsAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="10dd3-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="10dd3-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="10dd3-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="10dd3-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="10dd3-110">Data type: string</span></span>  
  
 <span data-ttu-id="10dd3-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="10dd3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="10dd3-112">Especifica si el enlace para un servicio admite contratos.</span><span class="sxs-lookup"><span data-stu-id="10dd3-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="10dd3-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="10dd3-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="10dd3-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="10dd3-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="10dd3-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="10dd3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="10dd3-116">Especifica si el enlace admite mensajes ordenados.</span><span class="sxs-lookup"><span data-stu-id="10dd3-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="10dd3-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="10dd3-117">TargetContract</span></span>  
 <span data-ttu-id="10dd3-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="10dd3-118">Data type: string</span></span>  
  
 <span data-ttu-id="10dd3-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="10dd3-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="10dd3-120">El contrato al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="10dd3-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10dd3-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10dd3-121">Requirements</span></span>  
  
|<span data-ttu-id="10dd3-122">MOF</span><span class="sxs-lookup"><span data-stu-id="10dd3-122">MOF</span></span>|<span data-ttu-id="10dd3-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="10dd3-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="10dd3-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="10dd3-124">Namespace</span></span>|<span data-ttu-id="10dd3-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="10dd3-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10dd3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="10dd3-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
