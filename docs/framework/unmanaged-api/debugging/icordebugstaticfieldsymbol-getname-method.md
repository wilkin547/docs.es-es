---
title: 'ICorDebugStaticFieldSymbol:: GetName (método)'
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: e961ae064bd5bb2c97175b4506ddd8c0f17d3b32
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131778"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="2a0b2-102">ICorDebugStaticFieldSymbol:: GetName (método)</span><span class="sxs-lookup"><span data-stu-id="2a0b2-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="2a0b2-103">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="2a0b2-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a0b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a0b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a0b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a0b2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2a0b2-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="2a0b2-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2a0b2-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="2a0b2-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="2a0b2-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="2a0b2-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a0b2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a0b2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a0b2-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2a0b2-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a0b2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a0b2-111">Requirements</span></span>  
 <span data-ttu-id="2a0b2-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a0b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a0b2-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a0b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a0b2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a0b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a0b2-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a0b2-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0b2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a0b2-116">See also</span></span>

- [<span data-ttu-id="2a0b2-117">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a0b2-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="2a0b2-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2a0b2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
