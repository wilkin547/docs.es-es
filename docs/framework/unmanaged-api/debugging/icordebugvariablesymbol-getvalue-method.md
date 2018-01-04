---
title: "ICorDebugVariableSymbol::GetValue (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ede5c92a13ad12667d282cf53a7498683dccfb92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="4695b-102">ICorDebugVariableSymbol::GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="4695b-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="4695b-103">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="4695b-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4695b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4695b-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4695b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4695b-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="4695b-106">[in] Desplazamiento inicial de la variable de la que se va a leer el valor.</span><span class="sxs-lookup"><span data-stu-id="4695b-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="4695b-107">Este parámetro se utiliza cuando se leen campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="4695b-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="4695b-108">[in] Tamaño del argumento `context` en bytes.</span><span class="sxs-lookup"><span data-stu-id="4695b-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="4695b-109">[in] Contexto del subproceso utilizado para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="4695b-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="4695b-110">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="4695b-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="4695b-111">[out] Número de bytes escritos realmente en el búfer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="4695b-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4695b-112">[out] Matriz de bytes que contiene el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="4695b-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4695b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4695b-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4695b-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4695b-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4695b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4695b-115">Requirements</span></span>  
 <span data-ttu-id="4695b-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4695b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4695b-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4695b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4695b-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4695b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4695b-119">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4695b-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4695b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4695b-120">See Also</span></span>  
 [<span data-ttu-id="4695b-121">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4695b-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="4695b-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4695b-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
