---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40bdc27337daae02795137fc3ac67575787018c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="deliveryrequirementsattribute"></a><span data-ttu-id="b7e27-102">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="b7e27-102">DeliveryRequirementsAttribute</span></span>
<span data-ttu-id="b7e27-103">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="b7e27-103">DeliveryRequirementsAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7e27-104">Syntax</span></span>  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b7e27-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7e27-105">Methods</span></span>  
 <span data-ttu-id="b7e27-106">La clase DeliveryRequirementsAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b7e27-106">The DeliveryRequirementsAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b7e27-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b7e27-107">Properties</span></span>  
 <span data-ttu-id="b7e27-108">La clase DeliveryRequirementsAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7e27-108">The DeliveryRequirementsAttribute class has the following properties:</span></span>  
  
### <a name="queueddeliveryrequirements"></a><span data-ttu-id="b7e27-109">QueuedDeliveryRequirements</span><span class="sxs-lookup"><span data-stu-id="b7e27-109">QueuedDeliveryRequirements</span></span>  
 <span data-ttu-id="b7e27-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b7e27-110">Data type: string</span></span>  
  
 <span data-ttu-id="b7e27-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7e27-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7e27-112">Especifica si el enlace para un servicio admite contratos.</span><span class="sxs-lookup"><span data-stu-id="b7e27-112">Specifies whether the binding for a service supports contracts.</span></span>  
  
### <a name="requireordereddelivery"></a><span data-ttu-id="b7e27-113">RequireOrderedDelivery</span><span class="sxs-lookup"><span data-stu-id="b7e27-113">RequireOrderedDelivery</span></span>  
 <span data-ttu-id="b7e27-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b7e27-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b7e27-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7e27-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7e27-116">Especifica si el enlace admite mensajes ordenados.</span><span class="sxs-lookup"><span data-stu-id="b7e27-116">Specifies whether the binding supports ordered messages.</span></span>  
  
### <a name="targetcontract"></a><span data-ttu-id="b7e27-117">TargetContract</span><span class="sxs-lookup"><span data-stu-id="b7e27-117">TargetContract</span></span>  
 <span data-ttu-id="b7e27-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b7e27-118">Data type: string</span></span>  
  
 <span data-ttu-id="b7e27-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b7e27-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b7e27-120">El contrato al que se aplica.</span><span class="sxs-lookup"><span data-stu-id="b7e27-120">The contract to which it applies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7e27-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7e27-121">Requirements</span></span>  
  
|<span data-ttu-id="b7e27-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b7e27-122">MOF</span></span>|<span data-ttu-id="b7e27-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b7e27-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b7e27-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b7e27-124">Namespace</span></span>|<span data-ttu-id="b7e27-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b7e27-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7e27-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7e27-126">See Also</span></span>  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
