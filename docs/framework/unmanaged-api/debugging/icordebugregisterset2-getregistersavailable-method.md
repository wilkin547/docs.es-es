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
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378221"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="b6bce-102">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="b6bce-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="b6bce-103">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="b6bce-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6bce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6bce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6bce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6bce-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="b6bce-106">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="b6bce-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="b6bce-107">enuncia Matriz de bytes, cada bit de la que corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="b6bce-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="b6bce-108">Si hay un registro disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="b6bce-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6bce-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b6bce-109">Remarks</span></span>  
 <span data-ttu-id="b6bce-110">Los valores de la enumeración CorDebugRegister (especifican los registros de distintos microprocesadores.</span><span class="sxs-lookup"><span data-stu-id="b6bce-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="b6bce-111">Los cinco bits superiores de cada valor son el índice de la `availableRegChunks` matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="b6bce-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="b6bce-112">Los tres bits inferiores de cada valor identifican la posición de bit dentro del byte indexado.</span><span class="sxs-lookup"><span data-stu-id="b6bce-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="b6bce-113">Dado un `CorDebugRegister` valor que especifica un registro determinado, la posición del registro en la máscara se determina de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6bce-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="b6bce-114">Extraiga el índice necesario para tener acceso al byte correcto de la `availableRegChunks` matriz:</span><span class="sxs-lookup"><span data-stu-id="b6bce-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="b6bce-115">`CorDebugRegister`valor >> 3</span><span class="sxs-lookup"><span data-stu-id="b6bce-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="b6bce-116">Extrae la posición de bit en el byte indizado, donde el bit cero es el bit menos significativo:</span><span class="sxs-lookup"><span data-stu-id="b6bce-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="b6bce-117">`CorDebugRegister`valor & 7</span><span class="sxs-lookup"><span data-stu-id="b6bce-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6bce-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6bce-118">Requirements</span></span>  
 <span data-ttu-id="b6bce-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6bce-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6bce-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6bce-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6bce-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6bce-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6bce-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6bce-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6bce-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6bce-123">See also</span></span>

- [<span data-ttu-id="b6bce-124">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6bce-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="b6bce-125">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6bce-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
