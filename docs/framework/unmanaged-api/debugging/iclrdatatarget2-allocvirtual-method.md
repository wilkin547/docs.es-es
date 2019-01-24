---
title: ICLRDataTarget2::AllocVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9fc894cdd12e58689fb6b010820bb24d14a9541
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543752"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="daedf-102">ICLRDataTarget2::AllocVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="daedf-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="daedf-103">Llamado por los servicios de acceso a datos de common language runtime (CLR) para asignar memoria en el espacio de direcciones de este proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="daedf-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daedf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="daedf-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daedf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="daedf-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="daedf-106">[in] Un `CLRDATA_ADDRESS` valor que especifica la dirección inicial solicitada de la asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="daedf-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="daedf-107">[in] El tamaño, en bytes, de la asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="daedf-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="daedf-108">[in] Marcas que controlan la asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="daedf-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="daedf-109">Consulte Win32 `VirtualAlloc` función.</span><span class="sxs-lookup"><span data-stu-id="daedf-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="daedf-110">[in] Los atributos de protección de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="daedf-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="daedf-111">Consulte Win32 `VirtualAlloc` función.</span><span class="sxs-lookup"><span data-stu-id="daedf-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="daedf-112">[out] Un puntero a un `CLRDATA_ADDRESS` valor que especifica la dirección inicial real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="daedf-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daedf-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="daedf-113">Remarks</span></span>  
 <span data-ttu-id="daedf-114">El `AllocVirtual` método actúa como un contenedor lógico para Win32 `VirtualAlloc` función.</span><span class="sxs-lookup"><span data-stu-id="daedf-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="daedf-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="daedf-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daedf-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="daedf-116">Requirements</span></span>  
 <span data-ttu-id="daedf-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daedf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daedf-118">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="daedf-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="daedf-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daedf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daedf-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daedf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daedf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="daedf-121">See also</span></span>
- [<span data-ttu-id="daedf-122">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="daedf-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="daedf-123">FreeVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="daedf-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
