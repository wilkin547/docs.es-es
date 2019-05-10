---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662822"
---
# <a name="activitytransfer"></a><span data-ttu-id="88bf9-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="88bf9-102">ActivityTransfer</span></span>
<span data-ttu-id="88bf9-103">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="88bf9-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88bf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88bf9-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="88bf9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="88bf9-105">Methods</span></span>  
 <span data-ttu-id="88bf9-106">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="88bf9-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="88bf9-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="88bf9-107">Properties</span></span>  
 <span data-ttu-id="88bf9-108">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="88bf9-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="88bf9-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="88bf9-109">ActivityID</span></span>  
  
- <span data-ttu-id="88bf9-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="88bf9-110">Data type: object</span></span>  
    <span data-ttu-id="88bf9-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="88bf9-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="88bf9-112">Id. de actividad</span><span class="sxs-lookup"><span data-stu-id="88bf9-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="88bf9-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="88bf9-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="88bf9-114">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="88bf9-114">Data type: object</span></span>  
    <span data-ttu-id="88bf9-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="88bf9-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="88bf9-116">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="88bf9-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88bf9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88bf9-117">Requirements</span></span>  
  
|<span data-ttu-id="88bf9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="88bf9-118">MOF</span></span>|<span data-ttu-id="88bf9-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="88bf9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="88bf9-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="88bf9-120">Namespace</span></span>|<span data-ttu-id="88bf9-121">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="88bf9-121">Defined in root\ServiceModel.</span></span>|
