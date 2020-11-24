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
ms.openlocfilehash: 04b3e73e2166efb2ec0821d21da3da4c53b0ca4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688658"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="2c4f6-102">IAssemblyName::SetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="2c4f6-102">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="2c4f6-103">Establece el valor de la propiedad a la que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="2c4f6-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c4f6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c4f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c4f6-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="2c4f6-106">de Identificador único de la propiedad cuyo valor se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="2c4f6-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="2c4f6-107">de Valor al que se va a establecer la propiedad a la que hace referencia `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="2c4f6-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="2c4f6-108">de Tamaño, en bytes, de `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="2c4f6-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c4f6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c4f6-109">Requirements</span></span>  

 <span data-ttu-id="2c4f6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c4f6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c4f6-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2c4f6-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2c4f6-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c4f6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4f6-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c4f6-113">See also</span></span>

- [<span data-ttu-id="2c4f6-114">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c4f6-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
