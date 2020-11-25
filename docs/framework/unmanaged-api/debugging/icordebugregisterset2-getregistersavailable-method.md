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
ms.openlocfilehash: cb56ea817d4045c19793a6290d68ae8b6236f14a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712327"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="4a075-102">ICorDebugRegisterSet2::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="4a075-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>

<span data-ttu-id="4a075-103">Obtiene una matriz de bytes que proporciona un mapa de bits de los registros disponibles.</span><span class="sxs-lookup"><span data-stu-id="4a075-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a075-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a075-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a075-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a075-105">Parameters</span></span>  

 `numChunks`  
 <span data-ttu-id="4a075-106">[in] Tamaño de la matriz `availableRegChunks`.</span><span class="sxs-lookup"><span data-stu-id="4a075-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="4a075-107">enuncia Matriz de bytes, cada bit de la que corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="4a075-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="4a075-108">Si hay un registro disponible, se establece el bit correspondiente del registro.</span><span class="sxs-lookup"><span data-stu-id="4a075-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a075-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a075-109">Remarks</span></span>  

 <span data-ttu-id="4a075-110">Los valores de la enumeración CorDebugRegister (especifican los registros de distintos microprocesadores.</span><span class="sxs-lookup"><span data-stu-id="4a075-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="4a075-111">Los cinco bits superiores de cada valor son el índice de la `availableRegChunks` matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="4a075-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="4a075-112">Los tres bits inferiores de cada valor identifican la posición de bit dentro del byte indexado.</span><span class="sxs-lookup"><span data-stu-id="4a075-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="4a075-113">Dado un `CorDebugRegister` valor que especifica un registro determinado, la posición del registro en la máscara se determina de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a075-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="4a075-114">Extraiga el índice necesario para tener acceso al byte correcto de la `availableRegChunks` matriz:</span><span class="sxs-lookup"><span data-stu-id="4a075-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="4a075-115">`CorDebugRegister` valor >> 3</span><span class="sxs-lookup"><span data-stu-id="4a075-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="4a075-116">Extrae la posición de bit en el byte indizado, donde el bit cero es el bit menos significativo:</span><span class="sxs-lookup"><span data-stu-id="4a075-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="4a075-117">`CorDebugRegister` valor & 7</span><span class="sxs-lookup"><span data-stu-id="4a075-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a075-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a075-118">Requirements</span></span>  

 <span data-ttu-id="4a075-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a075-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a075-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a075-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a075-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a075-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a075-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a075-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a075-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a075-123">See also</span></span>

- [<span data-ttu-id="4a075-124">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a075-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="4a075-125">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a075-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
