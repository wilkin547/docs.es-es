---
title: IAssemblyName::GetProperty (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9af0773c2ef066c103f823e4d28c0fd6e9eadc24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086564"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="44089-102">IAssemblyName::GetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="44089-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="44089-103">Obtiene un puntero a la propiedad al que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="44089-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44089-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44089-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44089-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44089-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="44089-106">[in] El identificador único para la propiedad solicitada.</span><span class="sxs-lookup"><span data-stu-id="44089-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="44089-107">[out] Los datos de la propiedad devuelta.</span><span class="sxs-lookup"><span data-stu-id="44089-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="44089-108">[in, out] El tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="44089-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44089-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44089-109">Requirements</span></span>  
 <span data-ttu-id="44089-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44089-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44089-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="44089-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="44089-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44089-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44089-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="44089-113">See also</span></span>

- [<span data-ttu-id="44089-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="44089-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
