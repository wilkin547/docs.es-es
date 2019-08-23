---
title: ICorDebugVariableSymbol::GetValue (método)
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b72b9dbeff6aa06a132dc7ec3ddd9477553c4c2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967993"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="f1401-102">ICorDebugVariableSymbol::GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="f1401-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="f1401-103">Obtiene el valor de una variable como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="f1401-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1401-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1401-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f1401-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1401-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="f1401-106">[in] Desplazamiento inicial de la variable de la que se va a leer el valor.</span><span class="sxs-lookup"><span data-stu-id="f1401-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="f1401-107">Este parámetro se utiliza cuando se leen campos de miembro de un objeto.</span><span class="sxs-lookup"><span data-stu-id="f1401-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="f1401-108">[in] Tamaño del argumento `context` en bytes.</span><span class="sxs-lookup"><span data-stu-id="f1401-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="f1401-109">[in] Contexto del subproceso utilizado para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="f1401-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="f1401-110">[in] Tamaño del búfer `pValue` en bytes.</span><span class="sxs-lookup"><span data-stu-id="f1401-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="f1401-111">[out] Número de bytes escritos realmente en el búfer `pValue`.</span><span class="sxs-lookup"><span data-stu-id="f1401-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f1401-112">[out] Matriz de bytes que contiene el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="f1401-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1401-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1401-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1401-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f1401-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1401-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1401-115">Requirements</span></span>  
 <span data-ttu-id="f1401-116">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1401-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1401-117">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f1401-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1401-118">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1401-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1401-119">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1401-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1401-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1401-120">See also</span></span>

- [<span data-ttu-id="f1401-121">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1401-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="f1401-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f1401-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
