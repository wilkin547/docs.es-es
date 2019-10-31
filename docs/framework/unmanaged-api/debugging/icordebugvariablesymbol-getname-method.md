---
title: 'ICorDebugVariableSymbol:: GetName (método)'
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 9bc32d3372710b4c4e92aa89df5e6e7839ad3078
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121013"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="4e0f4-102">ICorDebugVariableSymbol:: GetName (método)</span><span class="sxs-lookup"><span data-stu-id="4e0f4-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="4e0f4-103">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="4e0f4-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e0f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e0f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e0f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e0f4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4e0f4-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="4e0f4-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4e0f4-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="4e0f4-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e0f4-108">Puntero a una matriz de caracteres que contiene el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="4e0f4-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e0f4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e0f4-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e0f4-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4e0f4-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e0f4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e0f4-111">Requirements</span></span>  
 <span data-ttu-id="4e0f4-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e0f4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e0f4-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e0f4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e0f4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e0f4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e0f4-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e0f4-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0f4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e0f4-116">See also</span></span>

- [<span data-ttu-id="4e0f4-117">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e0f4-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="4e0f4-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4e0f4-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
