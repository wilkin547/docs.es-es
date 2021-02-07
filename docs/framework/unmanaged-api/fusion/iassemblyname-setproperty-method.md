---
description: 'Más información sobre: IAssemblyName:: SetProperty (método)'
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
ms.openlocfilehash: cab132c2cd8a0744a2a946a1d8b21f49012c6eac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760696"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="5fd4e-103">IAssemblyName::SetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="5fd4e-103">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="5fd4e-104">Establece el valor de la propiedad a la que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="5fd4e-104">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fd4e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fd4e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fd4e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fd4e-106">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="5fd4e-107">de Identificador único de la propiedad cuyo valor se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="5fd4e-107">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="5fd4e-108">de Valor al que se va a establecer la propiedad a la que hace referencia `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="5fd4e-108">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="5fd4e-109">de Tamaño, en bytes, de `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="5fd4e-109">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fd4e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fd4e-110">Requirements</span></span>  

 <span data-ttu-id="5fd4e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fd4e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fd4e-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5fd4e-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5fd4e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd4e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd4e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fd4e-114">See also</span></span>

- [<span data-ttu-id="5fd4e-115">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fd4e-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
