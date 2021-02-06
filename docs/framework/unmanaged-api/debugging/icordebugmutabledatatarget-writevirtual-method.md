---
description: 'Más información sobre: ICorDebugMutableDataTarget:: WriteVirtual ((método)'
title: ICorDebugMutableDataTarget::WriteVirtual (método)
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 3f3400456b7af51f4b24d7e14e35d641f03a8bfd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637825"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="86f99-103">ICorDebugMutableDataTarget::WriteVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="86f99-103">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>

<span data-ttu-id="86f99-104">Escribe la memoria en el espacio de direcciones de procesos de destino.</span><span class="sxs-lookup"><span data-stu-id="86f99-104">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86f99-105">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86f99-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86f99-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="86f99-107">[in] Dirección a la que se va a escribir el contenido de `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="86f99-107">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="86f99-108">[in] Puntero a una matriz de bytes que contiene los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="86f99-108">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="86f99-109">[in] Número de bytes en `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="86f99-109">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86f99-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86f99-110">Return Value</span></span>  

 <span data-ttu-id="86f99-111">`S_OK`, si la operación se realiza correctamente o cualquier otro `HRESULT`, en caso de error.</span><span class="sxs-lookup"><span data-stu-id="86f99-111">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86f99-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86f99-112">Remarks</span></span>  

 <span data-ttu-id="86f99-113">Si no se puede escribir bytes, la llamada al método produce un error sin cambiar los bytes en el espacio de la dirección de destino</span><span class="sxs-lookup"><span data-stu-id="86f99-113">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="86f99-114">(de lo contrario, el destino estaría en un estado incoherente que haría que las futuras depuraciones resultasen poco fiables).</span><span class="sxs-lookup"><span data-stu-id="86f99-114">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f99-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86f99-115">Requirements</span></span>  

 <span data-ttu-id="86f99-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86f99-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86f99-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86f99-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86f99-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86f99-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86f99-119">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86f99-119">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f99-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="86f99-120">See also</span></span>

- [<span data-ttu-id="86f99-121">Interfaz ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="86f99-121">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="86f99-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="86f99-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
