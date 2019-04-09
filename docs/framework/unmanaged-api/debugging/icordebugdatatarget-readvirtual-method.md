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
ms.openlocfilehash: 4749bfee22e58ad7c3ca29ec992da88493ca2c5c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111532"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="c11a1-102">ICorDebugDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="c11a1-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="c11a1-103">Obtiene un bloque de memoria contigua a partir de la dirección especificada y lo devuelve en el búfer proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c11a1-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c11a1-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c11a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c11a1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c11a1-106">[in] La dirección de inicio de la memoria solicitada.</span><span class="sxs-lookup"><span data-stu-id="c11a1-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="c11a1-107">[out] El búfer donde se almacenará la memoria.</span><span class="sxs-lookup"><span data-stu-id="c11a1-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="c11a1-108">[in] El número de bytes que se obtenga de la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="c11a1-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="c11a1-109">[out] El número de bytes leídos realmente en la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="c11a1-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="c11a1-110">Esto puede ser menor que `bytesRequested`.</span><span class="sxs-lookup"><span data-stu-id="c11a1-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c11a1-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c11a1-111">Remarks</span></span>  
 <span data-ttu-id="c11a1-112">Si se puede leer el primer byte (en la dirección de inicio especificada), la llamada debe devolver correctamente (para admitir la lectura eficaz de estructuras de datos con longitud autodescriptiva, como cadenas terminadas en null).</span><span class="sxs-lookup"><span data-stu-id="c11a1-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c11a1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c11a1-113">Requirements</span></span>  
 <span data-ttu-id="c11a1-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c11a1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c11a1-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c11a1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c11a1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c11a1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c11a1-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c11a1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c11a1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c11a1-118">See also</span></span>

- [<span data-ttu-id="c11a1-119">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c11a1-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="c11a1-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c11a1-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c11a1-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="c11a1-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
