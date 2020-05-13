---
title: ICorDebugRegisterSet::GetRegisters (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 40de06d47654337542d2c80dc325f8201335312a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379154"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="793c0-102">ICorDebugRegisterSet::GetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="793c0-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="793c0-103">Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="793c0-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="793c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="793c0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="793c0-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="793c0-106">de Máscara de bits que especifica los valores de registro que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="793c0-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="793c0-107">Cada bit corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="793c0-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="793c0-108">Si un bit se establece en uno, se recupera el valor del registro; de lo contrario, no se recupera el valor del registro.</span><span class="sxs-lookup"><span data-stu-id="793c0-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="793c0-109">de Número de valores de registro que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="793c0-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="793c0-110">enuncia Matriz de `CORDB_REGISTER` objetos, cada uno de los cuales recibe un valor de un registro.</span><span class="sxs-lookup"><span data-stu-id="793c0-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="793c0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="793c0-111">Remarks</span></span>  
 <span data-ttu-id="793c0-112">El tamaño de la matriz debe ser igual al número de bits establecido en uno en la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="793c0-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="793c0-113">El `regCount` parámetro especifica el número de elementos en el búfer que recibirán los valores de registro.</span><span class="sxs-lookup"><span data-stu-id="793c0-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="793c0-114">Si el `regCount` valor es demasiado pequeño para el número de registros indicados por la máscara, los registros con mayor número se truncarán del conjunto.</span><span class="sxs-lookup"><span data-stu-id="793c0-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="793c0-115">Si el `regCount` valor es demasiado grande, los elementos no utilizados no se `regBuffer` modificarán.</span><span class="sxs-lookup"><span data-stu-id="793c0-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="793c0-116">Si la máscara de bits especifica un registro que no está disponible, `GetRegisters` devuelve un valor indeterminado para ese registro.</span><span class="sxs-lookup"><span data-stu-id="793c0-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="793c0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="793c0-117">Requirements</span></span>  
 <span data-ttu-id="793c0-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="793c0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="793c0-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="793c0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="793c0-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="793c0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="793c0-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="793c0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793c0-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="793c0-122">See also</span></span>

- [<span data-ttu-id="793c0-123">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="793c0-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="793c0-124">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="793c0-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
