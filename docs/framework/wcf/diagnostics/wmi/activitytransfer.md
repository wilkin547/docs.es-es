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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="bd99c-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="bd99c-102">ActivityTransfer</span></span>
<span data-ttu-id="bd99c-103">Evento de transferencia de actividad</span><span class="sxs-lookup"><span data-stu-id="bd99c-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd99c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd99c-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bd99c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bd99c-105">Methods</span></span>  
 <span data-ttu-id="bd99c-106">La clase ActivityTransfer no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="bd99c-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bd99c-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bd99c-107">Properties</span></span>  
 <span data-ttu-id="bd99c-108">La clase ActivityTransfer posee las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="bd99c-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="bd99c-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="bd99c-109">ActivityID</span></span>  
  
-   <span data-ttu-id="bd99c-110">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="bd99c-110">Data type: object</span></span>  
    <span data-ttu-id="bd99c-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bd99c-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="bd99c-112">Id. de actividad</span><span class="sxs-lookup"><span data-stu-id="bd99c-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="bd99c-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="bd99c-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="bd99c-114">Tipo de datos: objeto</span><span class="sxs-lookup"><span data-stu-id="bd99c-114">Data type: object</span></span>  
    <span data-ttu-id="bd99c-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bd99c-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="bd99c-116">Id. de actividad relacionada</span><span class="sxs-lookup"><span data-stu-id="bd99c-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd99c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd99c-117">Requirements</span></span>  
  
|<span data-ttu-id="bd99c-118">MOF</span><span class="sxs-lookup"><span data-stu-id="bd99c-118">MOF</span></span>|<span data-ttu-id="bd99c-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bd99c-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bd99c-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bd99c-120">Namespace</span></span>|<span data-ttu-id="bd99c-121">Se define en root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bd99c-121">Defined in root\ServiceModel.</span></span>|
