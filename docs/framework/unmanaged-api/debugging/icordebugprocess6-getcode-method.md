---
title: "Método ICorDebugProcess6::GetCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f532c52ac487915b76d624e62886a93db6d1eae4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="fe1ea-102">Método ICorDebugProcess6::GetCode</span><span class="sxs-lookup"><span data-stu-id="fe1ea-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="fe1ea-103">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe1ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe1ea-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe1ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe1ea-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="fe1ea-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que especifica la dirección inicial del segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="fe1ea-107">[out] Un puntero a la dirección de un objeto de "ICorDebugCode" que representa un segmento de código administrado.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe1ea-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe1ea-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe1ea-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fe1ea-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe1ea-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe1ea-110">Requirements</span></span>  
 <span data-ttu-id="fe1ea-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe1ea-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe1ea-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe1ea-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe1ea-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe1ea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe1ea-114">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe1ea-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe1ea-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe1ea-115">See Also</span></span>  
 [<span data-ttu-id="fe1ea-116">ICorDebugProcess6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe1ea-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="fe1ea-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fe1ea-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
