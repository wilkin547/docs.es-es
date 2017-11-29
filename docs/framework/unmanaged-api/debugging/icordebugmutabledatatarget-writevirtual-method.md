---
title: "ICorDebugMutableDataTarget::WriteVirtual (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9541a324c448312f50858ea0b1b284585d223edf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="ab6fb-102">ICorDebugMutableDataTarget::WriteVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="ab6fb-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="ab6fb-103">Escribe la memoria en el espacio de direcciones de procesos de destino.</span><span class="sxs-lookup"><span data-stu-id="ab6fb-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab6fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab6fb-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab6fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab6fb-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="ab6fb-106">[in] Dirección a la que se va a escribir el contenido de `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ab6fb-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="ab6fb-107">[in] Puntero a una matriz de bytes que contiene los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="ab6fb-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="ab6fb-108">[in] Número de bytes en `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ab6fb-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab6fb-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ab6fb-109">Return Value</span></span>  
 <span data-ttu-id="ab6fb-110">`S_OK`, si la operación se realiza correctamente o cualquier otro `HRESULT`, en caso de error.</span><span class="sxs-lookup"><span data-stu-id="ab6fb-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab6fb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab6fb-111">Remarks</span></span>  
 <span data-ttu-id="ab6fb-112">Si no se puede escribir bytes, la llamada al método produce un error sin cambiar los bytes en el espacio de la dirección de destino</span><span class="sxs-lookup"><span data-stu-id="ab6fb-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="ab6fb-113">(de lo contrario, el destino estaría en un estado incoherente que haría que las futuras depuraciones resultasen poco fiables).</span><span class="sxs-lookup"><span data-stu-id="ab6fb-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab6fb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab6fb-114">Requirements</span></span>  
 <span data-ttu-id="ab6fb-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab6fb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab6fb-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab6fb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab6fb-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab6fb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab6fb-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab6fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab6fb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab6fb-119">See Also</span></span>  
 [<span data-ttu-id="ab6fb-120">ICorDebugMutableDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab6fb-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="ab6fb-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ab6fb-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
