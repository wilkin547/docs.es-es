---
title: Método ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd5a2735a77813436ea4796a27003f4cb140c7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423486"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="19b6b-102">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="19b6b-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="19b6b-103">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="19b6b-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b6b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19b6b-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19b6b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19b6b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="19b6b-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="19b6b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="19b6b-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="19b6b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="19b6b-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="19b6b-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19b6b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19b6b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19b6b-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="19b6b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19b6b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19b6b-111">Requirements</span></span>  
 <span data-ttu-id="19b6b-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19b6b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19b6b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19b6b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19b6b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19b6b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19b6b-115">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19b6b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b6b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="19b6b-116">See Also</span></span>  
 [<span data-ttu-id="19b6b-117">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19b6b-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="19b6b-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="19b6b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
