---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26cd30be591c4167fa6a6e4d19ba9d1c909c6428
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145774"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="0e8aa-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue (Método)</span><span class="sxs-lookup"><span data-stu-id="0e8aa-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="0e8aa-103">Obtiene el valor de un argumento o una variable local, de los cuales la baja y menos significativos se almacenan en la ubicación de memoria y el registro especifican, respectivamente, para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e8aa-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e8aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e8aa-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="0e8aa-106">[in] Un valor de la enumeración "CorDebugRegister" que especifica el registro que contiene los bytes más significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="0e8aa-107">[in] Un `CORDB_ADDRESS` valor que especifica la ubicación de memoria que contiene los bytes menos significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="0e8aa-108">[in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="0e8aa-109">[in] Un `PCCOR_SIGNATURE` valor al que apunta a la firma de metadatos binaria del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0e8aa-110">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en la ubicación especificada del registro y la memoria.</span><span class="sxs-lookup"><span data-stu-id="0e8aa-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e8aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e8aa-111">Requirements</span></span>  
 <span data-ttu-id="0e8aa-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e8aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e8aa-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e8aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e8aa-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e8aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e8aa-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e8aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8aa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e8aa-116">See also</span></span>
