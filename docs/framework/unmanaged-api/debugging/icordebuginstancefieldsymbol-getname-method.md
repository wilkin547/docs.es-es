---
title: Método ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b1b3cc489c504942806b043fa2e3b76d5415d84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936937"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="a127d-102">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="a127d-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="a127d-103">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="a127d-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a127d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a127d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a127d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a127d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a127d-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a127d-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a127d-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a127d-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a127d-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="a127d-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a127d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a127d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a127d-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a127d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a127d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a127d-111">Requirements</span></span>  
 <span data-ttu-id="a127d-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a127d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a127d-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="a127d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a127d-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a127d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a127d-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a127d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a127d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a127d-116">See also</span></span>

- [<span data-ttu-id="a127d-117">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a127d-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="a127d-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a127d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
