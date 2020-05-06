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
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860701"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="db7d7-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="db7d7-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="db7d7-103">Enumera las áreas de memoria especificadas.</span><span class="sxs-lookup"><span data-stu-id="db7d7-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db7d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db7d7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db7d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db7d7-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="db7d7-106">de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.</span><span class="sxs-lookup"><span data-stu-id="db7d7-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="db7d7-107">La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.</span><span class="sxs-lookup"><span data-stu-id="db7d7-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="db7d7-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="db7d7-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="db7d7-109">de Un valor de la enumeración [clrdataenummemoryflags (](clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="db7d7-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db7d7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db7d7-110">Remarks</span></span>  
 <span data-ttu-id="db7d7-111">Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.</span><span class="sxs-lookup"><span data-stu-id="db7d7-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db7d7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db7d7-112">Requirements</span></span>  
 <span data-ttu-id="db7d7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db7d7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db7d7-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="db7d7-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="db7d7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db7d7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db7d7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db7d7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7d7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db7d7-117">See also</span></span>

- [<span data-ttu-id="db7d7-118">ICLRDataEnumMemoryRegions (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db7d7-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
