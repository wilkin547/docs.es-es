---
description: 'Más información sobre: ICLRDataTarget2:: Freevirtual ((método)'
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
ms.openlocfilehash: ef4048f421fcdc7d284663036f8cc9f2614f4e13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729255"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="d911c-103">ICLRDataTarget2::FreeVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="d911c-103">ICLRDataTarget2::FreeVirtual Method</span></span>

<span data-ttu-id="d911c-104">Lo llaman los servicios de acceso a datos de Common Language Runtime (CLR) para liberar memoria que se asignó previamente en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="d911c-104">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d911c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d911c-105">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d911c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d911c-106">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="d911c-107">de `CLRDATA_ADDRESS` Valor que especifica la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="d911c-107">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="d911c-108">de Tamaño, en bytes, de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="d911c-108">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="d911c-109">de Marcas que controlan la liberación de memoria.</span><span class="sxs-lookup"><span data-stu-id="d911c-109">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="d911c-110">Vea la `VirtualFree` función Win32.</span><span class="sxs-lookup"><span data-stu-id="d911c-110">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d911c-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d911c-111">Remarks</span></span>  

 <span data-ttu-id="d911c-112">El `FreeVirtual` método actúa como contenedor lógico de la función de Win32 `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="d911c-112">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="d911c-113">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="d911c-113">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d911c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d911c-114">Requirements</span></span>  

 <span data-ttu-id="d911c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d911c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d911c-116">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="d911c-116">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d911c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d911c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d911c-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d911c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d911c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d911c-119">See also</span></span>

- [<span data-ttu-id="d911c-120">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d911c-120">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="d911c-121">Método AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="d911c-121">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
