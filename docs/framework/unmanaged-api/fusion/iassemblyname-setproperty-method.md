---
title: IAssemblyName::SetProperty (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: ffa1fa2f5e141728a56f1b598a1aae9602b2ac86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108219"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="4c65d-102">IAssemblyName::SetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="4c65d-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="4c65d-103">Establece el valor de la propiedad a la que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="4c65d-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c65d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c65d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c65d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4c65d-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="4c65d-106">de Identificador único de la propiedad cuyo valor se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="4c65d-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="4c65d-107">de Valor al que se va a establecer la propiedad a la que hace referencia `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="4c65d-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="4c65d-108">de Tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="4c65d-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c65d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c65d-109">Requirements</span></span>  
 <span data-ttu-id="4c65d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c65d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c65d-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4c65d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4c65d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c65d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c65d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c65d-113">See also</span></span>

- [<span data-ttu-id="4c65d-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c65d-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
