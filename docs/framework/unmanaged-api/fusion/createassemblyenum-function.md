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
ms.openlocfilehash: 0e54027806cef07fad4740c3bf5226fd26c72570
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108776"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="7ddce-102">CreateAssemblyEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="7ddce-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="7ddce-103">Obtiene un puntero a una instancia de [IAssemblyEnum](iassemblyenum-interface.md) que puede enumerar los objetos del ensamblado con la [IAssemblyName](iassemblyname-interface.md)especificada.</span><span class="sxs-lookup"><span data-stu-id="7ddce-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ddce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ddce-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ddce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ddce-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="7ddce-106">enuncia Puntero a una ubicación de memoria que contiene el puntero `IAssemblyEnum` solicitado.</span><span class="sxs-lookup"><span data-stu-id="7ddce-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="7ddce-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="7ddce-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7ddce-108">`pUnkReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="7ddce-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="7ddce-109">de `IAssemblyName` del ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="7ddce-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="7ddce-110">Este nombre se utiliza para filtrar la enumeración.</span><span class="sxs-lookup"><span data-stu-id="7ddce-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="7ddce-111">Puede ser null para enumerar todos los ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7ddce-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7ddce-112">de Marcas para modificar el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="7ddce-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="7ddce-113">Este parámetro contiene exactamente un bit de la enumeración [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="7ddce-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7ddce-114">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="7ddce-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7ddce-115">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="7ddce-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ddce-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ddce-116">Remarks</span></span>  
 <span data-ttu-id="7ddce-117">El parámetro `dwFlags` contiene exactamente un bit de la enumeración `ASM_CACHE_FLAGS`.</span><span class="sxs-lookup"><span data-stu-id="7ddce-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ddce-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ddce-118">Requirements</span></span>  
 <span data-ttu-id="7ddce-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ddce-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ddce-120">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7ddce-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7ddce-121">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7ddce-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ddce-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ddce-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ddce-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ddce-123">See also</span></span>

- [<span data-ttu-id="7ddce-124">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ddce-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="7ddce-125">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ddce-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="7ddce-126">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="7ddce-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
