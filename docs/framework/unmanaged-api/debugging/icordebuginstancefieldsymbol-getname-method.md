---
title: Método ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: dd925cc213ed8a6c5d1def85b3e6335751c1b594
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178757"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="21f9f-102">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="21f9f-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="21f9f-103">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="21f9f-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21f9f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21f9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21f9f-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="21f9f-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="21f9f-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="21f9f-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="21f9f-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="21f9f-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="21f9f-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21f9f-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="21f9f-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21f9f-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="21f9f-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21f9f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21f9f-111">Requirements</span></span>  
 <span data-ttu-id="21f9f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21f9f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21f9f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21f9f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21f9f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21f9f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21f9f-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21f9f-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f9f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21f9f-116">See also</span></span>

- [<span data-ttu-id="21f9f-117">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="21f9f-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="21f9f-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="21f9f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
