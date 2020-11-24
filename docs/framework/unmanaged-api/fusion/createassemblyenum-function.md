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
ms.openlocfilehash: b7e3696121475885f5061bd96eb6905d7ccae734
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683178"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="3a9ce-102">CreateAssemblyEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="3a9ce-102">CreateAssemblyEnum Function</span></span>

<span data-ttu-id="3a9ce-103">Obtiene un puntero a una instancia de [IAssemblyEnum](iassemblyenum-interface.md) que puede enumerar los objetos del ensamblado con la [IAssemblyName](iassemblyname-interface.md)especificada.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a9ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a9ce-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a9ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a9ce-105">Parameters</span></span>  

 `pEnum`  
 <span data-ttu-id="3a9ce-106">enuncia Puntero a una ubicación de memoria que contiene el `IAssemblyEnum` puntero solicitado.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="3a9ce-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3a9ce-108">`pUnkReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="3a9ce-109">de `IAssemblyName` Del ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="3a9ce-110">Este nombre se utiliza para filtrar la enumeración.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="3a9ce-111">Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3a9ce-112">de Marcas para modificar el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="3a9ce-113">Este parámetro contiene exactamente un bit de la enumeración [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3a9ce-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3a9ce-114">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3a9ce-115">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a9ce-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a9ce-116">Remarks</span></span>  

 <span data-ttu-id="3a9ce-117">El `dwFlags` parámetro contiene exactamente un bit de la `ASM_CACHE_FLAGS` enumeración.</span><span class="sxs-lookup"><span data-stu-id="3a9ce-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a9ce-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a9ce-118">Requirements</span></span>  

 <span data-ttu-id="3a9ce-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a9ce-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a9ce-120">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3a9ce-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3a9ce-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a9ce-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a9ce-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a9ce-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9ce-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a9ce-123">See also</span></span>

- [<span data-ttu-id="3a9ce-124">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a9ce-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="3a9ce-125">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a9ce-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="3a9ce-126">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="3a9ce-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
