---
description: 'Más información sobre: ICorDebugRegisterSet2:: Getregisters ((método)'
title: ICorDebugRegisterSet2::GetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: 58af939b0e88185e2be23b69ca70d28e93ff873f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794798"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="0bf20-103">ICorDebugRegisterSet2:: Getregisters ((método)</span><span class="sxs-lookup"><span data-stu-id="0bf20-103">ICorDebugRegisterSet2::GetRegisters method</span></span>

<span data-ttu-id="0bf20-104">Obtiene el valor de cada registro (para la plataforma en la que se está ejecutando el código actualmente) especificado por la máscara de bits determinada.</span><span class="sxs-lookup"><span data-stu-id="0bf20-104">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf20-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bf20-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bf20-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0bf20-106">Parameters</span></span>

 `maskCount`  
 <span data-ttu-id="0bf20-107">de Tamaño, en bytes, de la `mask` matriz.</span><span class="sxs-lookup"><span data-stu-id="0bf20-107">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="0bf20-108">de Matriz de bytes, cada bit de la que corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="0bf20-108">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="0bf20-109">Si el bit es 1, se recuperará el valor del registro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0bf20-109">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="0bf20-110">de Número de valores de registro que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0bf20-110">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="0bf20-111">enuncia Matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe el valor de un registro.</span><span class="sxs-lookup"><span data-stu-id="0bf20-111">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bf20-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0bf20-112">Remarks</span></span>

 <span data-ttu-id="0bf20-113">El `GetRegisters` método devuelve una matriz de valores de los registros especificados por la máscara.</span><span class="sxs-lookup"><span data-stu-id="0bf20-113">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="0bf20-114">La matriz no contiene valores de registros cuyo bit de máscara no se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="0bf20-114">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="0bf20-115">Por lo tanto, el tamaño de la `regBuffer` matriz debe ser igual al número de 1 de la máscara.</span><span class="sxs-lookup"><span data-stu-id="0bf20-115">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="0bf20-116">Si el valor de `regCount` es demasiado pequeño para el número de registros indicados por la máscara, los valores de los registros con mayor número se truncarán del conjunto.</span><span class="sxs-lookup"><span data-stu-id="0bf20-116">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="0bf20-117">Si `regCount` es demasiado grande, los elementos no utilizados no se `regBuffer` modificarán.</span><span class="sxs-lookup"><span data-stu-id="0bf20-117">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="0bf20-118">Si la máscara indica un registro no disponible, se devolverá un valor indeterminado para ese registro.</span><span class="sxs-lookup"><span data-stu-id="0bf20-118">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="0bf20-119">El `ICorDebugRegisterSet2::GetRegisters` método es necesario para las plataformas que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="0bf20-119">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms that have more than 64 registers.</span></span> <span data-ttu-id="0bf20-120">Por ejemplo, IA64 tiene 128 registros de uso general y registros de punto flotante de 128, por lo que necesita más de 64 bits en la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="0bf20-120">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64 bits in the bit mask.</span></span>  
  
 <span data-ttu-id="0bf20-121">Si no tiene más de 64 registros, como sucede en plataformas como x86, el `GetRegisters` método simplemente convierte los bytes de la `mask` matriz de bytes en `ULONG64` y, a continuación, llama al método [ICorDebugRegisterSet:: getregisters (](icordebugregisterset-getregisters-method.md) , que toma la `ULONG64` máscara.</span><span class="sxs-lookup"><span data-stu-id="0bf20-121">If you don't have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bf20-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bf20-122">Requirements</span></span>

 <span data-ttu-id="0bf20-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bf20-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf20-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bf20-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bf20-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bf20-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bf20-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf20-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf20-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bf20-127">See also</span></span>

- [<span data-ttu-id="0bf20-128">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bf20-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="0bf20-129">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bf20-129">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
