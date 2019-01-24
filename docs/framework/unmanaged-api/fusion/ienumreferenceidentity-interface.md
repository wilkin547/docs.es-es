---
title: IEnumReferenceIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f2ea9d0e20cb67cc36d0b5883e483ce98941b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743223"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="05db5-102">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="05db5-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="05db5-103">Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="05db5-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05db5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="05db5-104">Methods</span></span>  
  
|<span data-ttu-id="05db5-105">Método</span><span class="sxs-lookup"><span data-stu-id="05db5-105">Method</span></span>|<span data-ttu-id="05db5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="05db5-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="05db5-107">Obtiene un puntero de interfaz a una nueva `IEnumReferenceIdentity` que contiene los mismos miembros que esto `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05db5-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="05db5-108">Obtiene el número especificado de `IReferenceIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="05db5-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="05db5-109">Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="05db5-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="05db5-110">Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.</span><span class="sxs-lookup"><span data-stu-id="05db5-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05db5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05db5-111">Requirements</span></span>  
 <span data-ttu-id="05db5-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05db5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05db5-113">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="05db5-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="05db5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05db5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05db5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="05db5-115">See also</span></span>
- [<span data-ttu-id="05db5-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="05db5-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="05db5-117">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="05db5-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
