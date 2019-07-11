---
title: ICorDebugDataTarget::ReadVirtual (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d42c85502c12d4d77694626a533c69af97da67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750263"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="9c02a-102">ICorDebugDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="9c02a-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="9c02a-103">Obtiene un bloque de memoria contigua a partir de la dirección especificada y lo devuelve en el búfer proporcionado.</span><span class="sxs-lookup"><span data-stu-id="9c02a-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c02a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c02a-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c02a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c02a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9c02a-106">[in] La dirección de inicio de la memoria solicitada.</span><span class="sxs-lookup"><span data-stu-id="9c02a-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="9c02a-107">[out] El búfer donde se almacenará la memoria.</span><span class="sxs-lookup"><span data-stu-id="9c02a-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="9c02a-108">[in] El número de bytes que se obtenga de la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="9c02a-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="9c02a-109">[out] El número de bytes leídos realmente en la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="9c02a-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="9c02a-110">Esto puede ser menor que `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="9c02a-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c02a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c02a-111">Remarks</span></span>  
 <span data-ttu-id="9c02a-112">Si se puede leer el primer byte (en la dirección de inicio especificada), la llamada debe devolver correctamente (para admitir la lectura eficaz de estructuras de datos con longitud autodescriptiva, como cadenas terminadas en null).</span><span class="sxs-lookup"><span data-stu-id="9c02a-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c02a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c02a-113">Requirements</span></span>  
 <span data-ttu-id="9c02a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c02a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c02a-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c02a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c02a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c02a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c02a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c02a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c02a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c02a-118">See also</span></span>

- [<span data-ttu-id="9c02a-119">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c02a-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="9c02a-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9c02a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9c02a-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="9c02a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
