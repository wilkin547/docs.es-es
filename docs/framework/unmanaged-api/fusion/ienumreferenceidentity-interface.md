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
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796433"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="1ffde-102">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ffde-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="1ffde-103">Actúa como un enumerador para una colección `IReferenceIdentity` de objetos.</span><span class="sxs-lookup"><span data-stu-id="1ffde-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ffde-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1ffde-104">Methods</span></span>  
  
|<span data-ttu-id="1ffde-105">Método</span><span class="sxs-lookup"><span data-stu-id="1ffde-105">Method</span></span>|<span data-ttu-id="1ffde-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1ffde-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="1ffde-107">Obtiene un puntero de interfaz a un `IEnumReferenceIdentity` nuevo que contiene los mismos miembros que `IEnumReferenceIdentity`este.</span><span class="sxs-lookup"><span data-stu-id="1ffde-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="1ffde-108">Obtiene el número especificado de `IReferenceIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="1ffde-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="1ffde-109">Mueve el puntero de instrucción al principio de este `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="1ffde-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="1ffde-110">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="1ffde-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ffde-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ffde-111">Requirements</span></span>  
 <span data-ttu-id="1ffde-112">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ffde-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ffde-113">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="1ffde-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1ffde-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ffde-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ffde-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ffde-115">See also</span></span>

- [<span data-ttu-id="1ffde-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="1ffde-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="1ffde-117">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ffde-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
