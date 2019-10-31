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
ms.openlocfilehash: 112d530c765fc74ab4ea767cb3168977d1b45f47
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138358"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="6d40e-102">ICorDebugRegisterSet::GetRegisters (Método)</span><span class="sxs-lookup"><span data-stu-id="6d40e-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="6d40e-103">Obtiene el valor de cada registro (en el equipo que está ejecutando código actualmente) especificado por la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="6d40e-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d40e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d40e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d40e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d40e-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="6d40e-106">de Máscara de bits que especifica los valores de registro que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="6d40e-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="6d40e-107">Cada bit corresponde a un registro.</span><span class="sxs-lookup"><span data-stu-id="6d40e-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="6d40e-108">Si un bit se establece en uno, se recupera el valor del registro; de lo contrario, no se recupera el valor del registro.</span><span class="sxs-lookup"><span data-stu-id="6d40e-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="6d40e-109">de Número de valores de registro que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="6d40e-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="6d40e-110">enuncia Matriz de objetos `CORDB_REGISTER`, cada uno de los cuales recibe un valor de un registro.</span><span class="sxs-lookup"><span data-stu-id="6d40e-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d40e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d40e-111">Remarks</span></span>  
 <span data-ttu-id="6d40e-112">El tamaño de la matriz debe ser igual al número de bits establecido en uno en la máscara de bits.</span><span class="sxs-lookup"><span data-stu-id="6d40e-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="6d40e-113">El parámetro `regCount` especifica el número de elementos en el búfer que recibirán los valores de registro.</span><span class="sxs-lookup"><span data-stu-id="6d40e-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="6d40e-114">Si el valor de `regCount` es demasiado pequeño para el número de registros indicados por la máscara, los registros con mayor número se truncarán del conjunto.</span><span class="sxs-lookup"><span data-stu-id="6d40e-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="6d40e-115">Si el valor `regCount` es demasiado grande, los elementos `regBuffer` no utilizados no se modificarán.</span><span class="sxs-lookup"><span data-stu-id="6d40e-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="6d40e-116">Si la máscara de bits especifica un registro que no está disponible, `GetRegisters` devuelve un valor indeterminado para ese registro.</span><span class="sxs-lookup"><span data-stu-id="6d40e-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d40e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d40e-117">Requirements</span></span>  
 <span data-ttu-id="6d40e-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d40e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d40e-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d40e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d40e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d40e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d40e-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d40e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d40e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d40e-122">See also</span></span>

- [<span data-ttu-id="6d40e-123">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d40e-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="6d40e-124">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d40e-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
