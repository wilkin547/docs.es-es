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
ms.openlocfilehash: f3872a2b03d3b22d695af1c104e9ae8ba8856990
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729010"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="097dd-102">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="097dd-102">IEnumDefinitionIdentity Interface</span></span>

<span data-ttu-id="097dd-103">Actúa como enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="097dd-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="097dd-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="097dd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="097dd-105">Methods</span></span>  
  
|<span data-ttu-id="097dd-106">Método</span><span class="sxs-lookup"><span data-stu-id="097dd-106">Method</span></span>|<span data-ttu-id="097dd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="097dd-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="097dd-108">Obtiene un puntero de interfaz a un nuevo `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que este `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="097dd-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="097dd-109">Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="097dd-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="097dd-110">Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="097dd-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="097dd-111">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="097dd-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="097dd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="097dd-112">Requirements</span></span>  

 <span data-ttu-id="097dd-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="097dd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="097dd-114">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="097dd-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="097dd-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="097dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097dd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="097dd-116">See also</span></span>

- [<span data-ttu-id="097dd-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="097dd-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="097dd-118">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="097dd-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
