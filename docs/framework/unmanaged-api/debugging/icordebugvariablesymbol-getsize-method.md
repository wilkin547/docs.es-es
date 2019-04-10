---
title: Icordebugvariablesymbol (método)
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027b3f773ff0ed0ca7bf9d193f97a3b060ea8494
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211847"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="0a9a8-102">Icordebugvariablesymbol (método)</span><span class="sxs-lookup"><span data-stu-id="0a9a8-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="0a9a8-103">Obtiene el tamaño de una variable en bytes.</span><span class="sxs-lookup"><span data-stu-id="0a9a8-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a9a8-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a9a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a9a8-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="0a9a8-106">Puntero a un entero de 32 bits sin signo que contiene el tamaño de la variable.</span><span class="sxs-lookup"><span data-stu-id="0a9a8-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a9a8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a9a8-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a9a8-108">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0a9a8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a9a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a9a8-109">Requirements</span></span>  
 <span data-ttu-id="0a9a8-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a9a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a9a8-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a9a8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a9a8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a9a8-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0a9a8-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0a9a8-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a9a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a9a8-114">See also</span></span>

- [<span data-ttu-id="0a9a8-115">Interfaz ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="0a9a8-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="0a9a8-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0a9a8-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
