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
ms.openlocfilehash: b30bd3e97af8d222f629c5b4f9f318a9b6379e78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181407"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="84be6-102">ICLRDataTarget2::FreeVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="84be6-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="84be6-103">Llamado por los servicios de acceso a datos de common language runtime (CLR) para liberar memoria previamente asignada en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="84be6-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84be6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84be6-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84be6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84be6-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="84be6-106">[in] Un `CLRDATA_ADDRESS` valor que especifica la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="84be6-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="84be6-107">[in] El tamaño, en bytes, de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="84be6-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="84be6-108">[in] Marcas que controlan la liberación de memoria.</span><span class="sxs-lookup"><span data-stu-id="84be6-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="84be6-109">Consulte Win32 `VirtualFree` función.</span><span class="sxs-lookup"><span data-stu-id="84be6-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84be6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84be6-110">Remarks</span></span>  
 <span data-ttu-id="84be6-111">El `FreeVirtual` método actúa como un contenedor lógico para Win32 `VirtualFree` función.</span><span class="sxs-lookup"><span data-stu-id="84be6-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="84be6-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="84be6-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84be6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84be6-113">Requirements</span></span>  
 <span data-ttu-id="84be6-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84be6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84be6-115">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="84be6-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="84be6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84be6-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="84be6-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="84be6-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84be6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="84be6-118">See also</span></span>

- [<span data-ttu-id="84be6-119">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84be6-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="84be6-120">Método AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="84be6-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
