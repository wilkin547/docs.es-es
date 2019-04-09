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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123492"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="aa6a0-102">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="aa6a0-103">Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa6a0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="aa6a0-104">Methods</span></span>  
  
|<span data-ttu-id="aa6a0-105">Método</span><span class="sxs-lookup"><span data-stu-id="aa6a0-105">Method</span></span>|<span data-ttu-id="aa6a0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa6a0-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="aa6a0-107">Obtiene un puntero de interfaz a una nueva `IEnumReferenceIdentity` que contiene los mismos miembros que esto `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="aa6a0-108">Obtiene el número especificado de `IReferenceIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="aa6a0-109">Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="aa6a0-110">Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.</span><span class="sxs-lookup"><span data-stu-id="aa6a0-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa6a0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa6a0-111">Requirements</span></span>  
 <span data-ttu-id="aa6a0-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa6a0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa6a0-113">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="aa6a0-113">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="aa6a0-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aa6a0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa6a0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa6a0-115">See also</span></span>

- [<span data-ttu-id="aa6a0-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="aa6a0-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="aa6a0-117">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa6a0-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
