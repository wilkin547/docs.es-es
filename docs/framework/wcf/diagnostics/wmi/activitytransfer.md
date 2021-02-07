---
description: 'Más información acerca de: ActivityTransfer'
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 28f7d1c0d1056327313e7aa6be293eb325d8f265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99758013"
---
# <a name="activitytransfer"></a><span data-ttu-id="6d8fc-103">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="6d8fc-103">ActivityTransfer</span></span>

<span data-ttu-id="6d8fc-104">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="6d8fc-104">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d8fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d8fc-105">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6d8fc-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="6d8fc-106">Methods</span></span>  

 <span data-ttu-id="6d8fc-107">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6d8fc-107">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6d8fc-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6d8fc-108">Properties</span></span>  

 <span data-ttu-id="6d8fc-109">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d8fc-109">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="6d8fc-110">Identificador de actividad</span><span class="sxs-lookup"><span data-stu-id="6d8fc-110">ActivityID</span></span>  
  
- <span data-ttu-id="6d8fc-111">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="6d8fc-111">Data type: object</span></span>  
    <span data-ttu-id="6d8fc-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6d8fc-112">Access type: Read-only</span></span>  
  
- <span data-ttu-id="6d8fc-113">Identificador de actividad</span><span class="sxs-lookup"><span data-stu-id="6d8fc-113">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="6d8fc-114">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="6d8fc-114">RelatedActivityID</span></span>  
  
- <span data-ttu-id="6d8fc-115">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="6d8fc-115">Data type: object</span></span>  
    <span data-ttu-id="6d8fc-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6d8fc-116">Access type: Read-only</span></span>  
  
- <span data-ttu-id="6d8fc-117">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="6d8fc-117">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d8fc-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d8fc-118">Requirements</span></span>  
  
|<span data-ttu-id="6d8fc-119">MOF</span><span class="sxs-lookup"><span data-stu-id="6d8fc-119">MOF</span></span>|<span data-ttu-id="6d8fc-120">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6d8fc-120">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6d8fc-121">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6d8fc-121">Namespace</span></span>|<span data-ttu-id="6d8fc-122">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6d8fc-122">Defined in root\ServiceModel.</span></span>|
