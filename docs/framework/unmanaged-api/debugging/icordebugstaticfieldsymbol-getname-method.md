---
title: ICorDebugStaticFieldSymbol::GetName (método)
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: b1f5ca266f51df730dfb840c7bf003c47f31ece9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178510"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="dd623-102">ICorDebugStaticFieldSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="dd623-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="dd623-103">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="dd623-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd623-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd623-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd623-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd623-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="dd623-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="dd623-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dd623-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="dd623-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="dd623-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="dd623-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd623-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dd623-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd623-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="dd623-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd623-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd623-111">Requirements</span></span>  
 <span data-ttu-id="dd623-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd623-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd623-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd623-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd623-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd623-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd623-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd623-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd623-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd623-116">See also</span></span>

- [<span data-ttu-id="dd623-117">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="dd623-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="dd623-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dd623-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
