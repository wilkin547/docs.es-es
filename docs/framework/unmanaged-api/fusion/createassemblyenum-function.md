---
title: "CreateAssemblyEnum (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyEnum
helpviewer_keywords: CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c229496a79b146b5dcac3d06fa3efd9237e39d3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="ba261-102">CreateAssemblyEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="ba261-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="ba261-103">Obtiene un puntero a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instancia que puede enumerar los objetos incluidos en el ensamblado con los valores especificados [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ba261-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba261-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba261-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba261-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba261-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="ba261-106">[out] Puntero a una ubicación de memoria que contiene solicitado `IAssemblyEnum` puntero.</span><span class="sxs-lookup"><span data-stu-id="ba261-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="ba261-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="ba261-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ba261-108">`pUnkReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="ba261-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="ba261-109">[in] El `IAssemblyName` del ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="ba261-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="ba261-110">Este nombre se utiliza para filtrar la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ba261-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="ba261-111">Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ba261-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ba261-112">[in] Marcadores para modificar el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="ba261-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="ba261-113">Este parámetro contiene exactamente un bit de la [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ba261-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ba261-114">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="ba261-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ba261-115">`pvReserved`debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="ba261-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba261-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba261-116">Remarks</span></span>  
 <span data-ttu-id="ba261-117">El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.</span><span class="sxs-lookup"><span data-stu-id="ba261-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba261-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba261-118">Requirements</span></span>  
 <span data-ttu-id="ba261-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba261-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba261-120">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ba261-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ba261-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba261-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba261-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba261-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba261-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba261-123">See Also</span></span>  
 [<span data-ttu-id="ba261-124">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba261-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [<span data-ttu-id="ba261-125">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba261-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="ba261-126">Funciones estáticas globales de fusión</span><span class="sxs-lookup"><span data-stu-id="ba261-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
