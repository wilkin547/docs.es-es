---
title: ICorDebugStaticFieldSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 6284a27921e0ba5bd3cedf07ef9f62348460ad06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677241"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="9cb51-102">ICorDebugStaticFieldSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="9cb51-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>

<span data-ttu-id="9cb51-103">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="9cb51-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cb51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cb51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9cb51-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="9cb51-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9cb51-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9cb51-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="9cb51-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9cb51-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="9cb51-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cb51-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9cb51-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cb51-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9cb51-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb51-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cb51-111">Requirements</span></span>  

 <span data-ttu-id="9cb51-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cb51-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cb51-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cb51-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cb51-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cb51-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cb51-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cb51-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb51-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cb51-116">See also</span></span>

- [<span data-ttu-id="9cb51-117">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="9cb51-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="9cb51-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9cb51-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
