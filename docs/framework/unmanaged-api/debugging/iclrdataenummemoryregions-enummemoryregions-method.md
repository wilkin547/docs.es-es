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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886f78a0561ebbd5470b7932123f67975d650693
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197352"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="a99bc-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="a99bc-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="a99bc-103">Enumera las áreas especificadas de la memoria.</span><span class="sxs-lookup"><span data-stu-id="a99bc-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a99bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a99bc-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a99bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a99bc-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="a99bc-106">[in] Un puntero a un [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instancia que se llama a este método para cada región de memoria que se va a enumerar para notificar al depurador el resultado.</span><span class="sxs-lookup"><span data-stu-id="a99bc-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="a99bc-107">La enumeración de áreas de memoria continúa incluso si la devolución de llamada indica un error.</span><span class="sxs-lookup"><span data-stu-id="a99bc-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="a99bc-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a99bc-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="a99bc-109">[in] Un valor de la [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeración que especifica las regiones de memoria que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="a99bc-109">[in] A value of the [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a99bc-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a99bc-110">Remarks</span></span>  
 <span data-ttu-id="a99bc-111">Este método usa especificado [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instancia para notificar al llamador de resultados.</span><span class="sxs-lookup"><span data-stu-id="a99bc-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a99bc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a99bc-112">Requirements</span></span>  
 <span data-ttu-id="a99bc-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a99bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a99bc-114">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="a99bc-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a99bc-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a99bc-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a99bc-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a99bc-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a99bc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a99bc-117">See also</span></span>

- [<span data-ttu-id="a99bc-118">ICLRDataEnumMemoryRegions (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a99bc-118">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
