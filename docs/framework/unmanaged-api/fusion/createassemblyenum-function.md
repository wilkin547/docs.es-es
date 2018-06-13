---
title: CreateAssemblyEnum (Función)
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2098d5d9ce1c01f232cf2904c1fd3e990dfbe2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432121"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="8f92f-102">CreateAssemblyEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="8f92f-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="8f92f-103">Obtiene un puntero a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instancia que puede enumerar los objetos incluidos en el ensamblado con los valores especificados [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8f92f-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f92f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f92f-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f92f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f92f-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="8f92f-106">[out] Puntero a una ubicación de memoria que contiene solicitado `IAssemblyEnum` puntero.</span><span class="sxs-lookup"><span data-stu-id="8f92f-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="8f92f-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="8f92f-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8f92f-108">`pUnkReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="8f92f-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="8f92f-109">[in] El `IAssemblyName` del ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="8f92f-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="8f92f-110">Este nombre se utiliza para filtrar la enumeración.</span><span class="sxs-lookup"><span data-stu-id="8f92f-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="8f92f-111">Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8f92f-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8f92f-112">[in] Marcadores para modificar el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="8f92f-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="8f92f-113">Este parámetro contiene exactamente un bit de la [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="8f92f-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8f92f-114">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="8f92f-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8f92f-115">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="8f92f-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f92f-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f92f-116">Remarks</span></span>  
 <span data-ttu-id="8f92f-117">El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.</span><span class="sxs-lookup"><span data-stu-id="8f92f-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f92f-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f92f-118">Requirements</span></span>  
 <span data-ttu-id="8f92f-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f92f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f92f-120">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8f92f-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8f92f-121">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f92f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f92f-122">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f92f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f92f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f92f-123">See Also</span></span>  
 [<span data-ttu-id="8f92f-124">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f92f-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [<span data-ttu-id="8f92f-125">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f92f-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="8f92f-126">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="8f92f-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
