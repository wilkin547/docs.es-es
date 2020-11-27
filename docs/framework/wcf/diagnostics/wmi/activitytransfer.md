---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291120"
---
# <a name="activitytransfer"></a><span data-ttu-id="a11b9-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="a11b9-102">ActivityTransfer</span></span>

<span data-ttu-id="a11b9-103">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="a11b9-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a11b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a11b9-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a11b9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a11b9-105">Methods</span></span>  

 <span data-ttu-id="a11b9-106">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="a11b9-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a11b9-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a11b9-107">Properties</span></span>  

 <span data-ttu-id="a11b9-108">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="a11b9-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="a11b9-109">Identificador de actividad</span><span class="sxs-lookup"><span data-stu-id="a11b9-109">ActivityID</span></span>  
  
- <span data-ttu-id="a11b9-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="a11b9-110">Data type: object</span></span>  
    <span data-ttu-id="a11b9-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a11b9-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="a11b9-112">Identificador de actividad</span><span class="sxs-lookup"><span data-stu-id="a11b9-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="a11b9-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="a11b9-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="a11b9-114">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="a11b9-114">Data type: object</span></span>  
    <span data-ttu-id="a11b9-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="a11b9-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="a11b9-116">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="a11b9-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a11b9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a11b9-117">Requirements</span></span>  
  
|<span data-ttu-id="a11b9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a11b9-118">MOF</span></span>|<span data-ttu-id="a11b9-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a11b9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a11b9-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a11b9-120">Namespace</span></span>|<span data-ttu-id="a11b9-121">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="a11b9-121">Defined in root\ServiceModel.</span></span>|
