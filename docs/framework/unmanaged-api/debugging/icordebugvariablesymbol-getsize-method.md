---
title: ICorDebugVariableSymbol::GetSize (método)
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01349b6418008db51c432d5c49f8491a44ab60d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419415"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="77c1c-102">ICorDebugVariableSymbol::GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="77c1c-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="77c1c-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="77c1c-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77c1c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77c1c-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77c1c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77c1c-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="77c1c-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="77c1c-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77c1c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77c1c-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77c1c-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="77c1c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77c1c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77c1c-109">Requirements</span></span>  
 <span data-ttu-id="77c1c-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77c1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77c1c-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77c1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77c1c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77c1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77c1c-113">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77c1c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c1c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="77c1c-114">See Also</span></span>  
 [<span data-ttu-id="77c1c-115">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="77c1c-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="77c1c-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="77c1c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
