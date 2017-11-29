---
title: "ICorDebugVariableSymbol::GetSize (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ea4a77b08b12c3f067d51f9dfe2c961192c3354
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="b2bb0-102">ICorDebugVariableSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="b2bb0-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="b2bb0-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2bb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2bb0-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2bb0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2bb0-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="b2bb0-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2bb0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2bb0-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2bb0-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b2bb0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2bb0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2bb0-109">Requirements</span></span>  
 <span data-ttu-id="b2bb0-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2bb0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2bb0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2bb0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2bb0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2bb0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2bb0-113">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2bb0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bb0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2bb0-114">See Also</span></span>  
 [<span data-ttu-id="b2bb0-115">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2bb0-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="b2bb0-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b2bb0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
