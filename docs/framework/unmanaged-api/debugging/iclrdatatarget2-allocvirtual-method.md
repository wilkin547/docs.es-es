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
ms.openlocfilehash: 6d3985919ea7e766db7d07e4ed81484851156ca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723676"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="fd2a7-102">ICLRDataTarget2::AllocVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="fd2a7-102">ICLRDataTarget2::AllocVirtual Method</span></span>

<span data-ttu-id="fd2a7-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para asignar memoria en el espacio de direcciones de este proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd2a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd2a7-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd2a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd2a7-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="fd2a7-106">de `CLRDATA_ADDRESS` Valor que especifica la dirección de inicio solicitada de la memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="fd2a7-107">de Tamaño, en bytes, de la memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="fd2a7-108">de Marcas que controlan la asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="fd2a7-109">Vea la `VirtualAlloc` función Win32.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="fd2a7-110">de Atributos de protección de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="fd2a7-111">Vea la `VirtualAlloc` función Win32.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="fd2a7-112">enuncia Un puntero a un `CLRDATA_ADDRESS` valor que especifica la dirección inicial real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd2a7-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd2a7-113">Remarks</span></span>  

 <span data-ttu-id="fd2a7-114">El `AllocVirtual` método actúa como contenedor lógico de la función de Win32 `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="fd2a7-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="fd2a7-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="fd2a7-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2a7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd2a7-116">Requirements</span></span>  

 <span data-ttu-id="fd2a7-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2a7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2a7-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="fd2a7-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="fd2a7-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd2a7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd2a7-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2a7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2a7-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd2a7-121">See also</span></span>

- [<span data-ttu-id="fd2a7-122">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd2a7-122">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="fd2a7-123">Método FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="fd2a7-123">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)
