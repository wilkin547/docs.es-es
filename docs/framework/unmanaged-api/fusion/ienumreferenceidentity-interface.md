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
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123492"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="8dc10-102">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8dc10-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="8dc10-103">Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="8dc10-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8dc10-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8dc10-104">Methods</span></span>  
  
|<span data-ttu-id="8dc10-105">Método</span><span class="sxs-lookup"><span data-stu-id="8dc10-105">Method</span></span>|<span data-ttu-id="8dc10-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dc10-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="8dc10-107">Obtiene un puntero de interfaz a una nueva `IEnumReferenceIdentity` que contiene los mismos miembros que esto `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="8dc10-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="8dc10-108">Obtiene el número especificado de `IReferenceIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="8dc10-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="8dc10-109">Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="8dc10-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="8dc10-110">Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.</span><span class="sxs-lookup"><span data-stu-id="8dc10-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8dc10-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dc10-111">Requirements</span></span>  
 <span data-ttu-id="8dc10-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dc10-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc10-113">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="8dc10-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="8dc10-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc10-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc10-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dc10-115">See also</span></span>

- [<span data-ttu-id="8dc10-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="8dc10-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="8dc10-117">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8dc10-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
