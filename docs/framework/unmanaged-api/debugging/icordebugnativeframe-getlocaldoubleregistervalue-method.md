---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13e1e3369c4e7a185c2167facc8514b5cfc85a85
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115874"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="e1f34-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="e1f34-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="e1f34-103">Obtiene el valor de un argumento o variable local que se almacena en los dos registros especificados para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="e1f34-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f34-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1f34-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1f34-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1f34-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="e1f34-106">[in] Un valor de la enumeración "CorDebugRegister" que especifica el registro que contiene los bytes más significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="e1f34-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="e1f34-107">[in] Un valor de la `CorDebugRegister` enumeración que especifica el registro que contiene los bytes menos significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="e1f34-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e1f34-108">[in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e1f34-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e1f34-109">[in] Un `PCCOR_SIGNATURE` valor al que apunta a la firma de metadatos binaria del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="e1f34-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e1f34-110">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en los registros especificados.</span><span class="sxs-lookup"><span data-stu-id="e1f34-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1f34-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1f34-111">Remarks</span></span>  
 <span data-ttu-id="e1f34-112">El `GetLocalDoubleRegisterValue` método puede utilizarse en un marco nativo o en un just-in-time (JIT)-marco compilado.</span><span class="sxs-lookup"><span data-stu-id="e1f34-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1f34-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1f34-113">Requirements</span></span>  
 <span data-ttu-id="e1f34-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1f34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1f34-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1f34-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1f34-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1f34-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1f34-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1f34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f34-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1f34-118">See also</span></span>
