---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 480670f19407321eb0928d07752936b2ece1f7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484193"
---
# <a name="activitytransfer"></a><span data-ttu-id="90ce5-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="90ce5-102">ActivityTransfer</span></span>
<span data-ttu-id="90ce5-103">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="90ce5-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ce5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90ce5-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="90ce5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="90ce5-105">Methods</span></span>  
 <span data-ttu-id="90ce5-106">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="90ce5-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="90ce5-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="90ce5-107">Properties</span></span>  
 <span data-ttu-id="90ce5-108">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="90ce5-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="90ce5-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="90ce5-109">ActivityID</span></span>  
  
-   <span data-ttu-id="90ce5-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="90ce5-110">Data type: object</span></span>  
    <span data-ttu-id="90ce5-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="90ce5-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="90ce5-112">Id. de actividad</span><span class="sxs-lookup"><span data-stu-id="90ce5-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="90ce5-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="90ce5-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="90ce5-114">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="90ce5-114">Data type: object</span></span>  
    <span data-ttu-id="90ce5-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="90ce5-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="90ce5-116">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="90ce5-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90ce5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90ce5-117">Requirements</span></span>  
  
|<span data-ttu-id="90ce5-118">MOF</span><span class="sxs-lookup"><span data-stu-id="90ce5-118">MOF</span></span>|<span data-ttu-id="90ce5-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="90ce5-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="90ce5-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="90ce5-120">Namespace</span></span>|<span data-ttu-id="90ce5-121">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="90ce5-121">Defined in root\ServiceModel.</span></span>|
