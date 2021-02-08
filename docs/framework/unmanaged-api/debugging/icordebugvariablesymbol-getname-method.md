---
description: 'Más información acerca de: ICorDebugVariableSymbol:: GetName (método)'
title: ICorDebugVariableSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 4a3ba1dfebd256dcbb8374634a52f1feca5d9611
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790599"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="9cd8e-103">ICorDebugVariableSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="9cd8e-103">ICorDebugVariableSymbol::GetName Method</span></span>

<span data-ttu-id="9cd8e-104">Obtiene el nombre de una variable.</span><span class="sxs-lookup"><span data-stu-id="9cd8e-104">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cd8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cd8e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cd8e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9cd8e-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="9cd8e-107">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9cd8e-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9cd8e-108">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9cd8e-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9cd8e-109">Puntero a una matriz de caracteres que contiene el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="9cd8e-109">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cd8e-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9cd8e-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cd8e-111">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9cd8e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cd8e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cd8e-112">Requirements</span></span>  

 <span data-ttu-id="9cd8e-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cd8e-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cd8e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cd8e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cd8e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cd8e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cd8e-116">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cd8e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd8e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cd8e-117">See also</span></span>

- [<span data-ttu-id="9cd8e-118">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="9cd8e-118">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="9cd8e-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9cd8e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
