---
description: 'Más información acerca de: Createassemblyenum ((función)'
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
ms.openlocfilehash: 47177fcf0cd9e1b492fa89b9fb80c5cdaaced689
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761148"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="8542d-103">CreateAssemblyEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="8542d-103">CreateAssemblyEnum Function</span></span>

<span data-ttu-id="8542d-104">Obtiene un puntero a una instancia de [IAssemblyEnum](iassemblyenum-interface.md) que puede enumerar los objetos del ensamblado con la [IAssemblyName](iassemblyname-interface.md)especificada.</span><span class="sxs-lookup"><span data-stu-id="8542d-104">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8542d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8542d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8542d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8542d-106">Parameters</span></span>  

 `pEnum`  
 <span data-ttu-id="8542d-107">enuncia Puntero a una ubicación de memoria que contiene el `IAssemblyEnum` puntero solicitado.</span><span class="sxs-lookup"><span data-stu-id="8542d-107">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="8542d-108">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="8542d-108">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8542d-109">`pUnkReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="8542d-109">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="8542d-110">de `IAssemblyName` Del ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="8542d-110">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="8542d-111">Este nombre se utiliza para filtrar la enumeración.</span><span class="sxs-lookup"><span data-stu-id="8542d-111">This name is used to filter the enumeration.</span></span> <span data-ttu-id="8542d-112">Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="8542d-112">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8542d-113">de Marcas para modificar el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="8542d-113">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="8542d-114">Este parámetro contiene exactamente un bit de la enumeración [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8542d-114">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8542d-115">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="8542d-115">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8542d-116">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="8542d-116">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8542d-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8542d-117">Remarks</span></span>  

 <span data-ttu-id="8542d-118">El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.</span><span class="sxs-lookup"><span data-stu-id="8542d-118">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8542d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8542d-119">Requirements</span></span>  

 <span data-ttu-id="8542d-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8542d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8542d-121">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8542d-121">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8542d-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8542d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8542d-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8542d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8542d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8542d-124">See also</span></span>

- [<span data-ttu-id="8542d-125">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8542d-125">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="8542d-126">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8542d-126">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="8542d-127">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="8542d-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
