---
title: "ICorDebugStaticFieldSymbol::GetName (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa999cf86c808e0fca430d181c0d9a9ba83f4a82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="57a35-102">ICorDebugStaticFieldSymbol::GetName (método)</span><span class="sxs-lookup"><span data-stu-id="57a35-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="57a35-103">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="57a35-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57a35-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57a35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57a35-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="57a35-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="57a35-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="57a35-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="57a35-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="57a35-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="57a35-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57a35-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57a35-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57a35-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="57a35-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57a35-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57a35-111">Requirements</span></span>  
 <span data-ttu-id="57a35-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57a35-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57a35-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57a35-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57a35-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57a35-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57a35-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a35-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a35-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="57a35-116">See Also</span></span>  
 [<span data-ttu-id="57a35-117">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="57a35-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="57a35-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="57a35-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
