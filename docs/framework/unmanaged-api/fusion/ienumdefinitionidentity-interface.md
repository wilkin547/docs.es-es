---
title: IEnumDefinitionIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88c2513229b6a4183cadbdc78e505910e01e152c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796472"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="57746-102">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57746-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="57746-103">Actúa como enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="57746-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57746-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57746-104">Syntax</span></span>  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="57746-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="57746-105">Methods</span></span>  
  
|<span data-ttu-id="57746-106">Método</span><span class="sxs-lookup"><span data-stu-id="57746-106">Method</span></span>|<span data-ttu-id="57746-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="57746-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="57746-108">Obtiene un puntero de interfaz a un `IEnumDefinitionIdentity` nuevo objeto que contiene los mismos miembros que `IEnumDefinitionIdentity`este.</span><span class="sxs-lookup"><span data-stu-id="57746-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="57746-109">Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="57746-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="57746-110">Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="57746-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="57746-111">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="57746-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57746-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57746-112">Requirements</span></span>  
 <span data-ttu-id="57746-113">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57746-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57746-114">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="57746-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="57746-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57746-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57746-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="57746-116">See also</span></span>

- [<span data-ttu-id="57746-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="57746-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="57746-118">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57746-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
