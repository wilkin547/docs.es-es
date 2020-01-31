---
title: ICorDebugVariableSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 172eea452442aa94ea010e2c434908ab8d040a93
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790923"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="550f6-102">ICorDebugVariableSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="550f6-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="550f6-103">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="550f6-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="550f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="550f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="550f6-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="550f6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="550f6-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="550f6-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="550f6-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="550f6-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="550f6-108">Puntero a una matriz de caracteres que contiene el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="550f6-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="550f6-109">Notas</span><span class="sxs-lookup"><span data-stu-id="550f6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="550f6-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="550f6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="550f6-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="550f6-111">Requirements</span></span>  
 <span data-ttu-id="550f6-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="550f6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="550f6-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="550f6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="550f6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="550f6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="550f6-115">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="550f6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="550f6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="550f6-116">See also</span></span>

- [<span data-ttu-id="550f6-117">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="550f6-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="550f6-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="550f6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
