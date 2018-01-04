---
title: "ICorDebugILCode2::GetLocalVarSigToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode2.GetLocalVarSigToken
api_location: mscordbi.dll
api_type: COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47004375194438b1ef0aaf61144ba6f16278545b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="40b0d-102">ICorDebugILCode2::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="40b0d-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="40b0d-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="40b0d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="40b0d-104">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="40b0d-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b0d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40b0d-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40b0d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40b0d-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="40b0d-107">[out] Puntero al token `mdSignature` de la firma de variable local para esta función, o `mdSignatureNil` si no hay ninguna firma (es decir, si la función no tiene variables locales).</span><span class="sxs-lookup"><span data-stu-id="40b0d-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40b0d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40b0d-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40b0d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40b0d-109">Requirements</span></span>  
 <span data-ttu-id="40b0d-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40b0d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40b0d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40b0d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40b0d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40b0d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40b0d-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40b0d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b0d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="40b0d-114">See Also</span></span>  
 [<span data-ttu-id="40b0d-115">ICorDebugILCode2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40b0d-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [<span data-ttu-id="40b0d-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="40b0d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
