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
ms.openlocfilehash: 0a36af5b411673081e74aa243ec8e0f8f876f238
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860475"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="f1849-102">ICLRDataTarget2::FreeVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="f1849-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="f1849-103">Lo llaman los servicios de acceso a datos de Common Language Runtime (CLR) para liberar memoria que se asignó previamente en el espacio de direcciones del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="f1849-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1849-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1849-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1849-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1849-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="f1849-106">de `CLRDATA_ADDRESS` Valor que especifica la dirección inicial de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="f1849-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="f1849-107">de Tamaño, en bytes, de la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="f1849-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="f1849-108">de Marcas que controlan la liberación de memoria.</span><span class="sxs-lookup"><span data-stu-id="f1849-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="f1849-109">Vea la función `VirtualFree` Win32.</span><span class="sxs-lookup"><span data-stu-id="f1849-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1849-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1849-110">Remarks</span></span>  
 <span data-ttu-id="f1849-111">El `FreeVirtual` método actúa como contenedor lógico de la función de `VirtualFree` Win32.</span><span class="sxs-lookup"><span data-stu-id="f1849-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="f1849-112">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="f1849-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1849-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1849-113">Requirements</span></span>  
 <span data-ttu-id="f1849-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1849-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1849-115">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="f1849-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f1849-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1849-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1849-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1849-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1849-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1849-118">See also</span></span>

- [<span data-ttu-id="f1849-119">ICLRDataTarget2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1849-119">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="f1849-120">Método AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="f1849-120">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
