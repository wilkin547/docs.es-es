---
title: ICorDebugStaticFieldSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 0e4c52ff1ae6113ee2c3990a9d91682e10141902
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791830"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="d6e2f-102">ICorDebugStaticFieldSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="d6e2f-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="d6e2f-103">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="d6e2f-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6e2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6e2f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d6e2f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d6e2f-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="d6e2f-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d6e2f-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="d6e2f-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="d6e2f-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="d6e2f-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e2f-109">Notas</span><span class="sxs-lookup"><span data-stu-id="d6e2f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6e2f-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d6e2f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e2f-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d6e2f-111">Requirements</span></span>  
 <span data-ttu-id="d6e2f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6e2f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e2f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e2f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e2f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e2f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e2f-115">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e2f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e2f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6e2f-116">See also</span></span>

- [<span data-ttu-id="d6e2f-117">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6e2f-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="d6e2f-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d6e2f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
