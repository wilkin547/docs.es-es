---
title: ICorDebugNativeFrame::GetLocalRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53c8290271391e52176f8364b592ce6b46faf71
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195948"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="3feb6-102">ICorDebugNativeFrame::GetLocalRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="3feb6-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="3feb6-103">Obtiene el valor de un argumento o variable local que se almacena en el registro especificado para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="3feb6-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3feb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3feb6-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3feb6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3feb6-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="3feb6-106">[in] Un valor de la enumeración "CorDebugRegister" que especifica el registro que contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="3feb6-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="3feb6-107">[in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3feb6-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="3feb6-108">[in] Un `PCCOR_SIGNATURE` valor al que apunta a la firma de metadatos binaria del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="3feb6-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="3feb6-109">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en el registro especificado.</span><span class="sxs-lookup"><span data-stu-id="3feb6-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3feb6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3feb6-110">Remarks</span></span>  
 <span data-ttu-id="3feb6-111">El `GetLocalRegisterValue` método puede utilizarse en un marco nativo o en un just-in-time (JIT)-marco compilado.</span><span class="sxs-lookup"><span data-stu-id="3feb6-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3feb6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3feb6-112">Requirements</span></span>  
 <span data-ttu-id="3feb6-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3feb6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3feb6-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3feb6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3feb6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3feb6-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3feb6-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3feb6-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3feb6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3feb6-117">See also</span></span>
