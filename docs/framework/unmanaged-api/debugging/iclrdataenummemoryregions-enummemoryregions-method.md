---
description: 'Más información acerca de: ICLRDataEnumMemoryRegions:: EnumMemoryRegions (método)'
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
ms.openlocfilehash: 48887defab38d6ac99c718e14646d39166927438
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785736"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="726b5-103">ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="726b5-103">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>

<span data-ttu-id="726b5-104">Enumera las áreas de memoria especificadas.</span><span class="sxs-lookup"><span data-stu-id="726b5-104">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="726b5-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="726b5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="726b5-106">Parameters</span></span>  

 `callback`  
 <span data-ttu-id="726b5-107">de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.</span><span class="sxs-lookup"><span data-stu-id="726b5-107">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="726b5-108">La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.</span><span class="sxs-lookup"><span data-stu-id="726b5-108">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="726b5-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="726b5-109">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="726b5-110">de Un valor de la enumeración [clrdataenummemoryflags (](clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="726b5-110">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="726b5-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="726b5-111">Remarks</span></span>  

 <span data-ttu-id="726b5-112">Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.</span><span class="sxs-lookup"><span data-stu-id="726b5-112">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="726b5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="726b5-113">Requirements</span></span>  

 <span data-ttu-id="726b5-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="726b5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726b5-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="726b5-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="726b5-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="726b5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="726b5-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726b5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="726b5-118">See also</span></span>

- [<span data-ttu-id="726b5-119">ICLRDataEnumMemoryRegions (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="726b5-119">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
