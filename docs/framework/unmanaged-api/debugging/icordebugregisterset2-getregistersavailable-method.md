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
ms.openlocfilehash: 00c9939b25f395010f6ea5832b405c3e9928a223
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792025"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="c7fba-102">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="c7fba-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="c7fba-103">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="c7fba-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7fba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7fba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7fba-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c7fba-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="c7fba-106">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="c7fba-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="c7fba-107">enuncia Matriz de bytes, cada bit de la que corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="c7fba-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="c7fba-108">Si hay un registro disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="c7fba-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7fba-109">Notas</span><span class="sxs-lookup"><span data-stu-id="c7fba-109">Remarks</span></span>  
 <span data-ttu-id="c7fba-110">Los valores de la enumeración CorDebugRegister (especifican los registros de distintos microprocesadores.</span><span class="sxs-lookup"><span data-stu-id="c7fba-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="c7fba-111">Los cinco bits superiores de cada valor son el índice de la matriz `availableRegChunks` de bytes.</span><span class="sxs-lookup"><span data-stu-id="c7fba-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="c7fba-112">Los tres bits inferiores de cada valor identifican la posición de bit dentro del byte indexado.</span><span class="sxs-lookup"><span data-stu-id="c7fba-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="c7fba-113">Dado un valor `CorDebugRegister` que especifica un registro determinado, la posición del registro en la máscara se determina de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7fba-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="c7fba-114">Extraiga el índice necesario para tener acceso al byte correcto en la matriz de `availableRegChunks`:</span><span class="sxs-lookup"><span data-stu-id="c7fba-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="c7fba-115">valor `CorDebugRegister` > > 3</span><span class="sxs-lookup"><span data-stu-id="c7fba-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="c7fba-116">Extrae la posición de bit en el byte indizado, donde el bit cero es el bit menos significativo:</span><span class="sxs-lookup"><span data-stu-id="c7fba-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="c7fba-117">`CorDebugRegister` valor & 7</span><span class="sxs-lookup"><span data-stu-id="c7fba-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7fba-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c7fba-118">Requirements</span></span>  
 <span data-ttu-id="c7fba-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7fba-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7fba-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7fba-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7fba-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7fba-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7fba-122">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7fba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fba-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7fba-123">See also</span></span>

- [<span data-ttu-id="c7fba-124">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7fba-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="c7fba-125">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7fba-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
