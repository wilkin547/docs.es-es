---
title: ICorDebugVariableSymbol::GetValue (método)
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: f217f7226d53a27363f66eb90a340fd3604a0217
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396518"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="f1997-102">ICorDebugVariableSymbol::GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="f1997-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="f1997-103">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="f1997-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1997-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1997-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f1997-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1997-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f1997-106">[in] Desplazamiento inicial de la variable de la que se va a leer el valor.</span><span class="sxs-lookup"><span data-stu-id="f1997-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="f1997-107">Este parámetro se utiliza cuando se leen campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="f1997-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="f1997-108">[in] Tamaño del argumento `context` en bytes.</span><span class="sxs-lookup"><span data-stu-id="f1997-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="f1997-109">[in] Contexto del subproceso utilizado para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="f1997-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="f1997-110">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="f1997-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="f1997-111">[out] Número de bytes escritos realmente en el búfer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f1997-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f1997-112">[out] Matriz de bytes que contiene el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="f1997-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1997-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1997-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1997-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f1997-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1997-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1997-115">Requirements</span></span>  
 <span data-ttu-id="f1997-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1997-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1997-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1997-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1997-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1997-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1997-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1997-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1997-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1997-120">See also</span></span>

- [<span data-ttu-id="f1997-121">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f1997-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f1997-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f1997-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
