---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f3db50a32fabc117c79eef5ac086a7798f86ed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="32eb2-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="32eb2-102">ActivityTransfer</span></span>
<span data-ttu-id="32eb2-103">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="32eb2-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32eb2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32eb2-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="32eb2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="32eb2-105">Methods</span></span>  
 <span data-ttu-id="32eb2-106">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="32eb2-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="32eb2-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="32eb2-107">Properties</span></span>  
 <span data-ttu-id="32eb2-108">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="32eb2-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="32eb2-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="32eb2-109">ActivityID</span></span>  
  
-   <span data-ttu-id="32eb2-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="32eb2-110">Data type: object</span></span>  
    <span data-ttu-id="32eb2-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="32eb2-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="32eb2-112">Id. de actividad</span><span class="sxs-lookup"><span data-stu-id="32eb2-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="32eb2-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="32eb2-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="32eb2-114">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="32eb2-114">Data type: object</span></span>  
    <span data-ttu-id="32eb2-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="32eb2-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="32eb2-116">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="32eb2-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32eb2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32eb2-117">Requirements</span></span>  
  
|<span data-ttu-id="32eb2-118">MOF</span><span class="sxs-lookup"><span data-stu-id="32eb2-118">MOF</span></span>|<span data-ttu-id="32eb2-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="32eb2-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="32eb2-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="32eb2-120">Namespace</span></span>|<span data-ttu-id="32eb2-121">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="32eb2-121">Defined in root\ServiceModel.</span></span>|
