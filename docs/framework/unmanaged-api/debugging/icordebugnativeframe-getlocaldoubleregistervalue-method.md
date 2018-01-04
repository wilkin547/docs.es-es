---
title: "ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ece07fcffbc0d0e6b8cf06cc04866c1b651e6a01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="6b0e4-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="6b0e4-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="6b0e4-103">Obtiene el valor de un argumento o una variable local que se almacena en los dos registros especificados para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b0e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b0e4-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b0e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b0e4-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="6b0e4-106">[in] Un valor de la enumeración "CorDebugRegister" que especifica el registro que contiene los bytes más significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="6b0e4-107">[in] Un valor de la `CorDebugRegister` enumeración que especifica el registro que contiene los bytes menos significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="6b0e4-108">[in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6b0e4-109">[in] Un `PCCOR_SIGNATURE` valor que señala a la firma de metadatos binaria del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6b0e4-110">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en los registros especificados.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b0e4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b0e4-111">Remarks</span></span>  
 <span data-ttu-id="6b0e4-112">El `GetLocalDoubleRegisterValue` método se puede utilizar en un marco nativo o un just-in-time (JIT)-marco compilado.</span><span class="sxs-lookup"><span data-stu-id="6b0e4-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b0e4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b0e4-113">Requirements</span></span>  
 <span data-ttu-id="6b0e4-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b0e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b0e4-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b0e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b0e4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b0e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b0e4-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b0e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b0e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b0e4-118">See Also</span></span>  
 
