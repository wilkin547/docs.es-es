---
description: 'Más información acerca de: ICorDebugVariableSymbol:: SetValue (método)'
title: ICorDebugVariableSymbol::SetValue (método)
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: aa36712defcf44039f17fe846113c15814549e09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800856"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="5af8c-103">ICorDebugVariableSymbol::SetValue (método)</span><span class="sxs-lookup"><span data-stu-id="5af8c-103">ICorDebugVariableSymbol::SetValue Method</span></span>

<span data-ttu-id="5af8c-104">Asigna el valor de una matriz de bytes a una variable.</span><span class="sxs-lookup"><span data-stu-id="5af8c-104">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af8c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5af8c-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5af8c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5af8c-106">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="5af8c-107">[in] Desplazamiento inicial de la variable en la que se va a establecer el valor.</span><span class="sxs-lookup"><span data-stu-id="5af8c-107">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="5af8c-108">Este parámetro se utiliza cuando se escribe en campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5af8c-108">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="5af8c-109">[in] Identificador de subproceso del subproceso cuyo contexto debe actualizarse para reflejar el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="5af8c-109">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="5af8c-110">[in] Tamaño en bytes del contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="5af8c-110">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="5af8c-111">[in] Contexto del subproceso utilizado para escribir el valor.</span><span class="sxs-lookup"><span data-stu-id="5af8c-111">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="5af8c-112">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="5af8c-112">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5af8c-113">[in] Búfer que contiene el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="5af8c-113">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5af8c-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5af8c-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5af8c-115">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5af8c-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af8c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5af8c-116">Requirements</span></span>  

 <span data-ttu-id="5af8c-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af8c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af8c-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5af8c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5af8c-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5af8c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5af8c-120">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af8c-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af8c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5af8c-121">See also</span></span>

- [<span data-ttu-id="5af8c-122">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="5af8c-122">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="5af8c-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5af8c-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
