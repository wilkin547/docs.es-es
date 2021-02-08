---
description: 'Más información acerca de: interfaz IEnumDefinitionIdentity ('
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
ms.openlocfilehash: 1055031c064115410334bbe4b20b48deee7ec4c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800167"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="b18ec-103">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b18ec-103">IEnumDefinitionIdentity Interface</span></span>

<span data-ttu-id="b18ec-104">Actúa como enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="b18ec-104">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b18ec-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="b18ec-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="b18ec-106">Methods</span></span>  
  
|<span data-ttu-id="b18ec-107">Método</span><span class="sxs-lookup"><span data-stu-id="b18ec-107">Method</span></span>|<span data-ttu-id="b18ec-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b18ec-108">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="b18ec-109">Obtiene un puntero de interfaz a un nuevo `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que este `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="b18ec-109">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="b18ec-110">Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="b18ec-110">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="b18ec-111">Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="b18ec-111">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="b18ec-112">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="b18ec-112">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b18ec-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b18ec-113">Requirements</span></span>  

 <span data-ttu-id="b18ec-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b18ec-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b18ec-115">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="b18ec-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b18ec-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b18ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18ec-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b18ec-117">See also</span></span>

- [<span data-ttu-id="b18ec-118">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="b18ec-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="b18ec-119">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b18ec-119">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
