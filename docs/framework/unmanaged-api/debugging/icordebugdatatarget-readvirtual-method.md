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
ms.openlocfilehash: 8fb0cfc72867653eaff65f3183dacf9191604290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679733"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="c7409-102">ICorDebugDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="c7409-102">ICorDebugDataTarget::ReadVirtual Method</span></span>

<span data-ttu-id="c7409-103">Obtiene un bloque de memoria contigua que comienza en la dirección especificada y lo devuelve en el búfer proporcionado.</span><span class="sxs-lookup"><span data-stu-id="c7409-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7409-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7409-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7409-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7409-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="c7409-106">de Dirección de inicio de la memoria solicitada.</span><span class="sxs-lookup"><span data-stu-id="c7409-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="c7409-107">enuncia Búfer donde se almacenará la memoria.</span><span class="sxs-lookup"><span data-stu-id="c7409-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="c7409-108">de Número de bytes que se van a obtener de la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="c7409-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="c7409-109">enuncia Número de bytes realmente leídos de la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="c7409-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="c7409-110">Puede ser menor que `bytesRequested` .</span><span class="sxs-lookup"><span data-stu-id="c7409-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7409-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7409-111">Remarks</span></span>  

 <span data-ttu-id="c7409-112">Si se puede leer el primer byte (en la dirección de inicio especificada), la llamada debe devolver Success (para admitir la lectura eficaz de estructuras de datos con longitud autodescriptiva, como cadenas terminadas en null).</span><span class="sxs-lookup"><span data-stu-id="c7409-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7409-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7409-113">Requirements</span></span>  

 <span data-ttu-id="c7409-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7409-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7409-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7409-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7409-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7409-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7409-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7409-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7409-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7409-118">See also</span></span>

- [<span data-ttu-id="c7409-119">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7409-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="c7409-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c7409-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c7409-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="c7409-121">Debugging</span></span>](index.md)
