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
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785638"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="aafa0-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="aafa0-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="aafa0-103">Enumera las áreas de memoria especificadas.</span><span class="sxs-lookup"><span data-stu-id="aafa0-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aafa0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aafa0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aafa0-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="aafa0-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="aafa0-106">de Puntero a una instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) a la que llama este método para cada región de memoria que se está enumerando para notificar al depurador del resultado.</span><span class="sxs-lookup"><span data-stu-id="aafa0-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="aafa0-107">La enumeración de las regiones de memoria continúa incluso si la devolución de llamada indica un error.</span><span class="sxs-lookup"><span data-stu-id="aafa0-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="aafa0-108">de No se usa.</span><span class="sxs-lookup"><span data-stu-id="aafa0-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="aafa0-109">de Un valor de la enumeración [clrdataenummemoryflags (](clrdataenummemoryflags-enumeration.md) que especifica las regiones de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="aafa0-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aafa0-110">Notas</span><span class="sxs-lookup"><span data-stu-id="aafa0-110">Remarks</span></span>  
 <span data-ttu-id="aafa0-111">Este método usa la instancia de [ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md) especificada para notificar a los resultados del llamador.</span><span class="sxs-lookup"><span data-stu-id="aafa0-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aafa0-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="aafa0-112">Requirements</span></span>  
 <span data-ttu-id="aafa0-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aafa0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aafa0-114">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="aafa0-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="aafa0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aafa0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aafa0-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aafa0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aafa0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="aafa0-117">See also</span></span>

- [<span data-ttu-id="aafa0-118">ICLRDataEnumMemoryRegions (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aafa0-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
