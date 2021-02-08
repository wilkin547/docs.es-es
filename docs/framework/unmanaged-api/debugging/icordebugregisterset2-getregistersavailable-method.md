---
description: 'Más información sobre: ICorDebugRegisterSet2:: Getregistersavailable ((método)'
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
ms.openlocfilehash: 3839647e69efd63aefd1aa154c457f292e684336
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790729"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="1339f-103">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="1339f-103">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>

<span data-ttu-id="1339f-104">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="1339f-104">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1339f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1339f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1339f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1339f-106">Parameters</span></span>  

 `numChunks`  
 <span data-ttu-id="1339f-107">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="1339f-107">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="1339f-108">enuncia Matriz de bytes, cada bit de la que corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="1339f-108">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="1339f-109">Si hay un registro disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="1339f-109">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1339f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1339f-110">Remarks</span></span>  

 <span data-ttu-id="1339f-111">Los valores de la enumeración CorDebugRegister (especifican los registros de distintos microprocesadores.</span><span class="sxs-lookup"><span data-stu-id="1339f-111">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="1339f-112">Los cinco bits superiores de cada valor son el índice de la `availableRegChunks` matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="1339f-112">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="1339f-113">Los tres bits inferiores de cada valor identifican la posición de bit dentro del byte indexado.</span><span class="sxs-lookup"><span data-stu-id="1339f-113">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="1339f-114">Dado un `CorDebugRegister` valor que especifica un registro determinado, la posición del registro en la máscara se determina de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="1339f-114">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="1339f-115">Extraiga el índice necesario para tener acceso al byte correcto de la `availableRegChunks` matriz:</span><span class="sxs-lookup"><span data-stu-id="1339f-115">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="1339f-116">`CorDebugRegister` valor >> 3</span><span class="sxs-lookup"><span data-stu-id="1339f-116">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="1339f-117">Extrae la posición de bit en el byte indizado, donde el bit cero es el bit menos significativo:</span><span class="sxs-lookup"><span data-stu-id="1339f-117">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="1339f-118">`CorDebugRegister` valor & 7</span><span class="sxs-lookup"><span data-stu-id="1339f-118">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1339f-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1339f-119">Requirements</span></span>  

 <span data-ttu-id="1339f-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1339f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1339f-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1339f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1339f-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1339f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1339f-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1339f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1339f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1339f-124">See also</span></span>

- [<span data-ttu-id="1339f-125">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1339f-125">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="1339f-126">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1339f-126">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
