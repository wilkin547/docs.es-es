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
ms.openlocfilehash: 3b9c2f0e20488826aca202b3ef454104964b8bb9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210350"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="f47ea-102">ICorDebugILCode2::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="f47ea-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="f47ea-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f47ea-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f47ea-104">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="f47ea-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f47ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f47ea-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f47ea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f47ea-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="f47ea-107">[out] Puntero al token `mdSignature` de la firma de variable local para esta función, o `mdSignatureNil` si no hay ninguna firma (es decir, si la función no tiene variables locales).</span><span class="sxs-lookup"><span data-stu-id="f47ea-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f47ea-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f47ea-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f47ea-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f47ea-109">Requirements</span></span>  
 <span data-ttu-id="f47ea-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f47ea-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f47ea-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f47ea-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f47ea-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f47ea-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f47ea-113">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f47ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f47ea-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f47ea-114">See also</span></span>

- [<span data-ttu-id="f47ea-115">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f47ea-115">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="f47ea-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f47ea-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
