---
description: 'Más información sobre: ICorDebugVariableSymbol:: GetValue (método)'
title: ICorDebugVariableSymbol::GetValue (método)
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: ccd7eae5cc4740e83d0210a903ba0e7778aa8896
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790573"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="fb618-103">ICorDebugVariableSymbol::GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="fb618-103">ICorDebugVariableSymbol::GetValue Method</span></span>

<span data-ttu-id="fb618-104">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="fb618-104">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb618-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb618-105">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb618-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb618-106">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="fb618-107">[in] Desplazamiento inicial de la variable de la que se va a leer el valor.</span><span class="sxs-lookup"><span data-stu-id="fb618-107">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="fb618-108">Este parámetro se utiliza cuando se leen campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="fb618-108">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="fb618-109">[in] Tamaño del argumento `context` en bytes.</span><span class="sxs-lookup"><span data-stu-id="fb618-109">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="fb618-110">[in] Contexto del subproceso utilizado para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="fb618-110">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="fb618-111">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="fb618-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="fb618-112">[out] Número de bytes escritos realmente en el búfer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="fb618-112">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="fb618-113">[out] Matriz de bytes que contiene el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="fb618-113">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb618-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fb618-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb618-115">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fb618-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb618-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb618-116">Requirements</span></span>  

 <span data-ttu-id="fb618-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb618-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb618-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb618-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb618-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb618-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb618-120">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb618-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb618-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb618-121">See also</span></span>

- [<span data-ttu-id="fb618-122">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="fb618-122">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="fb618-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fb618-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
