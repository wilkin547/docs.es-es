---
title: ICorDebugMutableDataTarget::WriteVirtual (método)
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 453ab23e292c5eab4a8300c32bf76743b787750d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709341"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="11a80-102">ICorDebugMutableDataTarget::WriteVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="11a80-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>

<span data-ttu-id="11a80-103">Escribe la memoria en el espacio de direcciones de procesos de destino.</span><span class="sxs-lookup"><span data-stu-id="11a80-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11a80-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11a80-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="11a80-106">[in] Dirección a la que se va a escribir el contenido de `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="11a80-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="11a80-107">[in] Puntero a una matriz de bytes que contiene los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="11a80-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="11a80-108">[in] Número de bytes en `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="11a80-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11a80-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11a80-109">Return Value</span></span>  

 <span data-ttu-id="11a80-110">`S_OK`, si la operación se realiza correctamente o cualquier otro `HRESULT`, en caso de error.</span><span class="sxs-lookup"><span data-stu-id="11a80-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a80-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11a80-111">Remarks</span></span>  

 <span data-ttu-id="11a80-112">Si no se puede escribir bytes, la llamada al método produce un error sin cambiar los bytes en el espacio de la dirección de destino</span><span class="sxs-lookup"><span data-stu-id="11a80-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="11a80-113">(de lo contrario, el destino estaría en un estado incoherente que haría que las futuras depuraciones resultasen poco fiables).</span><span class="sxs-lookup"><span data-stu-id="11a80-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a80-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11a80-114">Requirements</span></span>  

 <span data-ttu-id="11a80-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a80-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a80-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11a80-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11a80-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11a80-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11a80-118">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a80-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a80-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11a80-119">See also</span></span>

- [<span data-ttu-id="11a80-120">Interfaz ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="11a80-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="11a80-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="11a80-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
