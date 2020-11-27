---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274054"
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="fb68a-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="fb68a-102">DeliveryRequirementsAttribute</span></span>

<span data-ttu-id="fb68a-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="fb68a-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb68a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb68a-104">Syntax</span></span>  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb68a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb68a-105">Methods</span></span>  

 <span data-ttu-id="fb68a-106">La clase DeliveryRequirementsAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fb68a-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb68a-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fb68a-107">Properties</span></span>  

 <span data-ttu-id="fb68a-108">La clase DeliveryRequirementsAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fb68a-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="fb68a-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="fb68a-109">QueuedDeliveryRequirements</span></span>  

 <span data-ttu-id="fb68a-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fb68a-110">Data type: string</span></span>  
  
 <span data-ttu-id="fb68a-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fb68a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb68a-112">Especifica si el enlace para un servicio admite contratos.</span><span class="sxs-lookup"><span data-stu-id="fb68a-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="fb68a-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="fb68a-113">RequireOrderedDelivery</span></span>  

 <span data-ttu-id="fb68a-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fb68a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb68a-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fb68a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb68a-116">Especifica si el enlace admite mensajes ordenados.</span><span class="sxs-lookup"><span data-stu-id="fb68a-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="fb68a-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="fb68a-117">TargetContract</span></span>  

 <span data-ttu-id="fb68a-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fb68a-118">Data type: string</span></span>  
  
 <span data-ttu-id="fb68a-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fb68a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb68a-120">El contrato al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="fb68a-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb68a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb68a-121">Requirements</span></span>  
  
|<span data-ttu-id="fb68a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="fb68a-122">MOF</span></span>|<span data-ttu-id="fb68a-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb68a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb68a-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fb68a-124">Namespace</span></span>|<span data-ttu-id="fb68a-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fb68a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb68a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb68a-126">See also</span></span>

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
