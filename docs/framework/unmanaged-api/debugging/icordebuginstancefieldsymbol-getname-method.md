---
title: Método ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d23bf14fbb3d75534ac2d4a43eca0fbf3e994ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161400"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="e9513-102">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="e9513-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="e9513-103">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="e9513-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9513-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9513-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9513-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9513-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e9513-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e9513-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e9513-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e9513-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e9513-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="e9513-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9513-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9513-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9513-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e9513-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9513-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9513-111">Requirements</span></span>  
 <span data-ttu-id="e9513-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9513-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9513-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9513-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9513-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9513-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e9513-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e9513-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e9513-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9513-116">See also</span></span>

- [<span data-ttu-id="e9513-117">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e9513-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="e9513-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e9513-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
