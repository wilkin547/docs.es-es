---
title: ICorDebugRegisterSet2::GetRegistersAvailable (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3a9cdb49c1a44dbc68cd4b7ccf4d4781ce5c539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421897"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="16a39-102">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="16a39-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="16a39-103">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="16a39-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16a39-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16a39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16a39-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="16a39-106">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="16a39-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="16a39-107">[out] Una matriz de bytes, cada bit de los cuales corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="16a39-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="16a39-108">Si un registro está disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="16a39-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16a39-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16a39-109">Remarks</span></span>  
 <span data-ttu-id="16a39-110">Los valores de la enumeración CorDebugRegister especifican los registros de diferentes microprocesadores.</span><span class="sxs-lookup"><span data-stu-id="16a39-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="16a39-111">Los bits de cinco superiores de cada valor son el índice en la `availableRegChunks` matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="16a39-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="16a39-112">Los tres bits inferiores de cada valor identifican la posición de bit dentro del byte indizado.</span><span class="sxs-lookup"><span data-stu-id="16a39-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="16a39-113">Dado un `CorDebugRegister` valor que especifica un registro determinado, la posición del registro en la máscara se determina como sigue:</span><span class="sxs-lookup"><span data-stu-id="16a39-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="16a39-114">Extraer el índice que se necesita para tener acceso al byte correcto en el `availableRegChunks` matriz:</span><span class="sxs-lookup"><span data-stu-id="16a39-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="16a39-115">`CorDebugRegister` valor >> 3</span><span class="sxs-lookup"><span data-stu-id="16a39-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="16a39-116">Extraiga la posición de bit dentro del byte indizado, donde bit cero es el bit menos significativo del sistema:</span><span class="sxs-lookup"><span data-stu-id="16a39-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="16a39-117">`CorDebugRegister` valor & 7</span><span class="sxs-lookup"><span data-stu-id="16a39-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16a39-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16a39-118">Requirements</span></span>  
 <span data-ttu-id="16a39-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16a39-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16a39-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16a39-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16a39-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16a39-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16a39-122">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16a39-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a39-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="16a39-123">See Also</span></span>  
 [<span data-ttu-id="16a39-124">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16a39-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="16a39-125">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16a39-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
