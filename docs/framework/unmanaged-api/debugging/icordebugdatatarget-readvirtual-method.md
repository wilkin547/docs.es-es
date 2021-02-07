---
description: 'Más información sobre: ICorDebugDataTarget:: Readvirtual ((método)'
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
ms.openlocfilehash: 4525ba1e5dc685813d963dab96879b886987f38f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710613"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="75df7-103">ICorDebugDataTarget::ReadVirtual (Método)</span><span class="sxs-lookup"><span data-stu-id="75df7-103">ICorDebugDataTarget::ReadVirtual Method</span></span>

<span data-ttu-id="75df7-104">Obtiene un bloque de memoria contigua que comienza en la dirección especificada y lo devuelve en el búfer proporcionado.</span><span class="sxs-lookup"><span data-stu-id="75df7-104">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75df7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75df7-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75df7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75df7-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="75df7-107">de Dirección de inicio de la memoria solicitada.</span><span class="sxs-lookup"><span data-stu-id="75df7-107">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="75df7-108">enuncia Búfer donde se almacenará la memoria.</span><span class="sxs-lookup"><span data-stu-id="75df7-108">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="75df7-109">de Número de bytes que se van a obtener de la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="75df7-109">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="75df7-110">enuncia Número de bytes realmente leídos de la dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="75df7-110">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="75df7-111">Puede ser menor que `bytesRequested` .</span><span class="sxs-lookup"><span data-stu-id="75df7-111">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75df7-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75df7-112">Remarks</span></span>  

 <span data-ttu-id="75df7-113">Si se puede leer el primer byte (en la dirección de inicio especificada), la llamada debe devolver Success (para admitir la lectura eficaz de estructuras de datos con longitud autodescriptiva, como cadenas terminadas en null).</span><span class="sxs-lookup"><span data-stu-id="75df7-113">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75df7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75df7-114">Requirements</span></span>  

 <span data-ttu-id="75df7-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75df7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75df7-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75df7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75df7-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75df7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75df7-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75df7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75df7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="75df7-119">See also</span></span>

- [<span data-ttu-id="75df7-120">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75df7-120">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="75df7-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="75df7-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="75df7-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="75df7-122">Debugging</span></span>](index.md)
