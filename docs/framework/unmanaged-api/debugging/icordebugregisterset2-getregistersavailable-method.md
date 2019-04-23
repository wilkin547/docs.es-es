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
ms.openlocfilehash: 1522d643a69c47eec03770a8f51756dd4250075a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309425"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="5e32d-102">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="5e32d-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="5e32d-103">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="5e32d-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e32d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e32d-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e32d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e32d-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="5e32d-106">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="5e32d-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="5e32d-107">[out] Una matriz de bytes, cada bit de los cuales corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="5e32d-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="5e32d-108">Si un registro está disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="5e32d-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e32d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e32d-109">Remarks</span></span>  
 <span data-ttu-id="5e32d-110">Los valores de la enumeración CorDebugRegister especifican los registros de microprocesadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="5e32d-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="5e32d-111">Los cinco bits superiores de cada valor son el índice en el `availableRegChunks` matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="5e32d-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="5e32d-112">Los tres bits inferiores de cada valor identifica la posición de bit dentro del byte indizado.</span><span class="sxs-lookup"><span data-stu-id="5e32d-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="5e32d-113">Dado un `CorDebugRegister` valor que especifica un registro determinado, la posición del registro de la máscara se determina como sigue:</span><span class="sxs-lookup"><span data-stu-id="5e32d-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="5e32d-114">Extraiga el índice necesario para tener acceso al byte correcto en el `availableRegChunks` matriz:</span><span class="sxs-lookup"><span data-stu-id="5e32d-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="5e32d-115">`CorDebugRegister` valor >> 3</span><span class="sxs-lookup"><span data-stu-id="5e32d-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="5e32d-116">Extraiga la posición de bit dentro del byte indizado, donde bits cero es el bit menos significativo:</span><span class="sxs-lookup"><span data-stu-id="5e32d-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="5e32d-117">`CorDebugRegister` valor & 7</span><span class="sxs-lookup"><span data-stu-id="5e32d-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e32d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e32d-118">Requirements</span></span>  
 <span data-ttu-id="5e32d-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e32d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e32d-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e32d-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e32d-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e32d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e32d-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e32d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e32d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e32d-123">See also</span></span>

- [<span data-ttu-id="5e32d-124">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e32d-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="5e32d-125">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e32d-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
