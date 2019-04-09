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
ms.openlocfilehash: 0ee807ae17e4d53d3f6f3963f5a91df0a2dddd0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099877"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="e01f1-102">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="e01f1-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="e01f1-103">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="e01f1-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e01f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e01f1-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e01f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e01f1-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="e01f1-106">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="e01f1-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="e01f1-107">[out] Una matriz de bytes, cada bit de los cuales corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="e01f1-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="e01f1-108">Si un registro está disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="e01f1-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e01f1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e01f1-109">Remarks</span></span>  
 <span data-ttu-id="e01f1-110">Los valores de la enumeración CorDebugRegister especifican los registros de microprocesadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="e01f1-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="e01f1-111">Los cinco bits superiores de cada valor son el índice en el `availableRegChunks` matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="e01f1-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="e01f1-112">Los tres bits inferiores de cada valor identifica la posición de bit dentro del byte indizado.</span><span class="sxs-lookup"><span data-stu-id="e01f1-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="e01f1-113">Dado un `CorDebugRegister` valor que especifica un registro determinado, la posición del registro de la máscara se determina como sigue:</span><span class="sxs-lookup"><span data-stu-id="e01f1-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="e01f1-114">Extraiga el índice necesario para tener acceso al byte correcto en el `availableRegChunks` matriz:</span><span class="sxs-lookup"><span data-stu-id="e01f1-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     `CorDebugRegister` <span data-ttu-id="e01f1-115">valor >> 3</span><span class="sxs-lookup"><span data-stu-id="e01f1-115">value >> 3</span></span>  
  
2.  <span data-ttu-id="e01f1-116">Extraiga la posición de bit dentro del byte indizado, donde bits cero es el bit menos significativo:</span><span class="sxs-lookup"><span data-stu-id="e01f1-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     `CorDebugRegister` <span data-ttu-id="e01f1-117">valor & 7</span><span class="sxs-lookup"><span data-stu-id="e01f1-117">value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e01f1-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e01f1-118">Requirements</span></span>  
 <span data-ttu-id="e01f1-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e01f1-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e01f1-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e01f1-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e01f1-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e01f1-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e01f1-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e01f1-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e01f1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e01f1-123">See also</span></span>

- [<span data-ttu-id="e01f1-124">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e01f1-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="e01f1-125">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e01f1-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
