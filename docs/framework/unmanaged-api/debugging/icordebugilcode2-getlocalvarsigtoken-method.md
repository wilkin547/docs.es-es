---
description: 'Más información sobre: ICorDebugILCode2:: Getlocalvarsigtoken ((método)'
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
ms.openlocfilehash: cdf2725274a132528123534ddd36ae95e265af44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791431"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="4e75b-103">ICorDebugILCode2::GetLocalVarSigToken (Método)</span><span class="sxs-lookup"><span data-stu-id="4e75b-103">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>

<span data-ttu-id="4e75b-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="4e75b-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4e75b-105">Obtiene el token de metadatos de la firma de variable local para la función que esta instancia representa.</span><span class="sxs-lookup"><span data-stu-id="4e75b-105">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e75b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e75b-106">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e75b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e75b-107">Parameters</span></span>  

 `pmdSig`  
 <span data-ttu-id="4e75b-108">[out] Puntero al token `mdSignature` de la firma de variable local para esta función, o `mdSignatureNil` si no hay ninguna firma (es decir, si la función no tiene variables locales).</span><span class="sxs-lookup"><span data-stu-id="4e75b-108">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e75b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4e75b-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e75b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e75b-110">Requirements</span></span>  

 <span data-ttu-id="4e75b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e75b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e75b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e75b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e75b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e75b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e75b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e75b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e75b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e75b-115">See also</span></span>

- [<span data-ttu-id="4e75b-116">ICorDebugILCode2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e75b-116">ICorDebugILCode2 Interface</span></span>](icordebugilcode2-interface.md)
- [<span data-ttu-id="4e75b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4e75b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
