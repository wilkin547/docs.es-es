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
ms.openlocfilehash: 34186ee8825c0981ec095cf855c76ff5f800907d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432359"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="d089a-102">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d089a-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="d089a-103">Actúa como el enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="d089a-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d089a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d089a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="d089a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d089a-105">Methods</span></span>  
  
|<span data-ttu-id="d089a-106">Método</span><span class="sxs-lookup"><span data-stu-id="d089a-106">Method</span></span>|<span data-ttu-id="d089a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d089a-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="d089a-108">Obtiene un puntero de interfaz a una nueva `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que esto `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d089a-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="d089a-109">Obtiene el número especificado de `IDefinitionIdentity` módulos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="d089a-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="d089a-110">Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d089a-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="d089a-111">Mueve el puntero de instrucción hacia delante el número especificado de elementos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="d089a-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d089a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d089a-112">Requirements</span></span>  
 <span data-ttu-id="d089a-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d089a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d089a-114">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d089a-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d089a-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d089a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d089a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d089a-116">See Also</span></span>  
 [<span data-ttu-id="d089a-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="d089a-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="d089a-118">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d089a-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
