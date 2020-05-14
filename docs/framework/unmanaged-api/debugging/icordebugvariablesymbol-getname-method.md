---
title: ICorDebugVariableSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: ea414a39e140c74df736764dbbb1bb3934bda78f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397129"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="e1f5c-102">ICorDebugVariableSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="e1f5c-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="e1f5c-103">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1f5c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1f5c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1f5c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e1f5c-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e1f5c-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e1f5c-108">Puntero a una matriz de caracteres que contiene el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1f5c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1f5c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1f5c-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e1f5c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1f5c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1f5c-111">Requirements</span></span>  
 <span data-ttu-id="e1f5c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1f5c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1f5c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1f5c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1f5c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1f5c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1f5c-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1f5c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f5c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1f5c-116">See also</span></span>

- [<span data-ttu-id="e1f5c-117">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="e1f5c-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="e1f5c-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e1f5c-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
