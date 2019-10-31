---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: 693ec07176f80711709cd9b85c6886bea8be74b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122965"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="8703c-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="8703c-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="8703c-103">Enumera las áreas de memoria especificadas.</span><span class="sxs-lookup"><span data-stu-id="8703c-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8703c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8703c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8703c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8703c-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="8703c-106">de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.</span><span class="sxs-lookup"><span data-stu-id="8703c-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="8703c-107">La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.</span><span class="sxs-lookup"><span data-stu-id="8703c-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="8703c-108">de No se usa.</span><span class="sxs-lookup"><span data-stu-id="8703c-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="8703c-109">de Un valor de la enumeración [clrdataenummemoryflags (](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8703c-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8703c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8703c-110">Remarks</span></span>  
 <span data-ttu-id="8703c-111">Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.</span><span class="sxs-lookup"><span data-stu-id="8703c-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8703c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8703c-112">Requirements</span></span>  
 <span data-ttu-id="8703c-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8703c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8703c-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="8703c-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8703c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8703c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8703c-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8703c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8703c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8703c-117">See also</span></span>

- [<span data-ttu-id="8703c-118">ICLRDataEnumMemoryRegions (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8703c-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
