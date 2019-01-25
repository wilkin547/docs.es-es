---
title: ICLRDataTarget2::FreeVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02bba59a1c4445b3e432d5e44f2bccc4b72ce1da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711660"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="4b3a8-102">ICLRDataTarget2::FreeVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="4b3a8-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="4b3a8-103">Llamado por los servicios de acceso a datos de common language runtime (CLR) para liberar memoria previamente asignada en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b3a8-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b3a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b3a8-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="4b3a8-106">[in] Un `CLRDATA_ADDRESS` valor que especifica la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="4b3a8-107">[in] El tamaño, en bytes, de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="4b3a8-108">[in] Marcas que controlan la liberación de memoria.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="4b3a8-109">Consulte Win32 `VirtualFree` función.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b3a8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b3a8-110">Remarks</span></span>  
 <span data-ttu-id="4b3a8-111">El `FreeVirtual` método actúa como un contenedor lógico para Win32 `VirtualFree` función.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="4b3a8-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="4b3a8-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b3a8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b3a8-113">Requirements</span></span>  
 <span data-ttu-id="4b3a8-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3a8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b3a8-115">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="4b3a8-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4b3a8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b3a8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b3a8-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3a8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3a8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b3a8-118">See also</span></span>
- [<span data-ttu-id="4b3a8-119">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b3a8-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="4b3a8-120">AllocVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="4b3a8-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
