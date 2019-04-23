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
ms.openlocfilehash: d19ca92db6f57a004dca54f6e22db10603c9498a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214850"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="258bc-102">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="258bc-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="258bc-103">Actúa como el enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="258bc-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="258bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="258bc-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="258bc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="258bc-105">Methods</span></span>  
  
|<span data-ttu-id="258bc-106">Método</span><span class="sxs-lookup"><span data-stu-id="258bc-106">Method</span></span>|<span data-ttu-id="258bc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="258bc-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="258bc-108">Obtiene un puntero de interfaz a una nueva `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que esto `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="258bc-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="258bc-109">Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="258bc-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="258bc-110">Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="258bc-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="258bc-111">Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.</span><span class="sxs-lookup"><span data-stu-id="258bc-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="258bc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="258bc-112">Requirements</span></span>  
 <span data-ttu-id="258bc-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="258bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="258bc-114">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="258bc-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="258bc-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="258bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="258bc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="258bc-116">See also</span></span>

- [<span data-ttu-id="258bc-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="258bc-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="258bc-118">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="258bc-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
