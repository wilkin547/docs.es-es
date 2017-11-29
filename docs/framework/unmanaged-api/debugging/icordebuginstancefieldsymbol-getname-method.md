---
title: "Método ICorDebugInstanceFieldSymbol::GetName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfd56230d391c44343bdb3f575247b07af1e98ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="34f69-102">Método ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="34f69-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="34f69-103">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="34f69-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34f69-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34f69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="34f69-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="34f69-106">[in] Número de caracteres del búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="34f69-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="34f69-107">[out] Puntero al número de caracteres escritos realmente en el búfer `szName`.</span><span class="sxs-lookup"><span data-stu-id="34f69-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="34f69-108">[out] Matriz de caracteres que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="34f69-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34f69-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34f69-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34f69-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="34f69-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f69-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34f69-111">Requirements</span></span>  
 <span data-ttu-id="34f69-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34f69-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f69-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34f69-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34f69-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34f69-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34f69-115">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f69-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f69-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="34f69-116">See Also</span></span>  
 [<span data-ttu-id="34f69-117">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="34f69-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="34f69-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="34f69-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
