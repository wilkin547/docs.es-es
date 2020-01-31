---
title: ICorDebugVariableSymbol::SetValue (método)
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: fe6b63e4c0706dd69478753b3512f606e73bee7c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790851"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="5e6c1-102">ICorDebugVariableSymbol::SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="5e6c1-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="5e6c1-103">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e6c1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e6c1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5e6c1-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="5e6c1-106">[in] Desplazamiento inicial de la variable en la que se va a establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="5e6c1-107">Este parámetro se utiliza cuando se escribe en campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="5e6c1-108">[in] Identificador de subproceso del subproceso cuyo contexto debe actualizarse para reflejar el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="5e6c1-109">[in] Tamaño en bytes del contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="5e6c1-110">[in] Contexto del subproceso utilizado para escribir el valor.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="5e6c1-111">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5e6c1-112">[in] Búfer que contiene el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e6c1-113">Notas</span><span class="sxs-lookup"><span data-stu-id="5e6c1-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e6c1-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5e6c1-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e6c1-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5e6c1-115">Requirements</span></span>  
 <span data-ttu-id="5e6c1-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e6c1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e6c1-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e6c1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e6c1-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e6c1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e6c1-119">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e6c1-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6c1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e6c1-120">See also</span></span>

- [<span data-ttu-id="5e6c1-121">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e6c1-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="5e6c1-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5e6c1-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
