---
title: IEnumReferenceIdentity (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49e1425e8e7e3d09dc36915916b887d2887dccff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="01682-102">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="01682-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="01682-103">Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="01682-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01682-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="01682-104">Methods</span></span>  
  
|<span data-ttu-id="01682-105">Método</span><span class="sxs-lookup"><span data-stu-id="01682-105">Method</span></span>|<span data-ttu-id="01682-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="01682-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="01682-107">Obtiene un puntero de interfaz a una nueva `IEnumReferenceIdentity` que contiene los mismos miembros que esto `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="01682-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="01682-108">Obtiene el número especificado de `IReferenceIdentity` módulos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="01682-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="01682-109">Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="01682-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="01682-110">Mueve el puntero de instrucción hacia delante el número especificado de elementos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="01682-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01682-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01682-111">Requirements</span></span>  
 <span data-ttu-id="01682-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01682-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01682-113">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="01682-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="01682-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01682-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01682-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="01682-115">See Also</span></span>  
 [<span data-ttu-id="01682-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="01682-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="01682-117">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01682-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
