---
title: ICorDebugILCode2::GetLocalVarSigToken (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9810a8a55fc9c5296bffa5106551f9734dcd61bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199913"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="accef-102">ICorDebugILCode2::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="accef-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="accef-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="accef-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="accef-104">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="accef-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="accef-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="accef-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="accef-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="accef-107">[out] Puntero al token `mdSignature` de la firma de variable local para esta función, o `mdSignatureNil` si no hay ninguna firma (es decir, si la función no tiene variables locales).</span><span class="sxs-lookup"><span data-stu-id="accef-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="accef-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="accef-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accef-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="accef-109">Requirements</span></span>  
 <span data-ttu-id="accef-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accef-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="accef-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="accef-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="accef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="accef-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accef-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="accef-114">See also</span></span>

- [<span data-ttu-id="accef-115">ICorDebugILCode2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="accef-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="accef-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="accef-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
