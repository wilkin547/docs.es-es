---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034436"
---
# <a name="activitytransfer"></a><span data-ttu-id="1cd4c-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="1cd4c-102">ActivityTransfer</span></span>
<span data-ttu-id="1cd4c-103">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="1cd4c-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cd4c-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1cd4c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1cd4c-105">Methods</span></span>  
 <span data-ttu-id="1cd4c-106">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1cd4c-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1cd4c-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1cd4c-107">Properties</span></span>  
 <span data-ttu-id="1cd4c-108">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cd4c-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="1cd4c-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="1cd4c-109">ActivityID</span></span>  
  
-   <span data-ttu-id="1cd4c-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="1cd4c-110">Data type: object</span></span>  
    <span data-ttu-id="1cd4c-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1cd4c-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="1cd4c-112">Id. de actividad</span><span class="sxs-lookup"><span data-stu-id="1cd4c-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="1cd4c-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="1cd4c-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="1cd4c-114">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="1cd4c-114">Data type: object</span></span>  
    <span data-ttu-id="1cd4c-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1cd4c-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="1cd4c-116">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="1cd4c-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cd4c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cd4c-117">Requirements</span></span>  
  
|<span data-ttu-id="1cd4c-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1cd4c-118">MOF</span></span>|<span data-ttu-id="1cd4c-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1cd4c-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1cd4c-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1cd4c-120">Namespace</span></span>|<span data-ttu-id="1cd4c-121">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1cd4c-121">Defined in root\ServiceModel.</span></span>|
