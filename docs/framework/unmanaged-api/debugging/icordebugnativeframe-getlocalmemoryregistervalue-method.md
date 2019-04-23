---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b2244ec1be6fc0e5e19fac5adc7ecb38d68a0af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081156"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="e5ea6-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue (Método)</span><span class="sxs-lookup"><span data-stu-id="e5ea6-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="e5ea6-103">Obtiene el valor de un argumento o una variable local, de los cuales la palabra baja y más significativos se almacenan en el registro especificado y la ubicación de memoria, respectivamente, para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="e5ea6-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ea6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5ea6-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ea6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5ea6-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="e5ea6-106">[in] Un `CORDB_ADDRESS` valor que especifica la ubicación de memoria que contiene los bytes más significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="e5ea6-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="e5ea6-107">[in] Un valor de la enumeración "CorDebugRegister" que especifica el registro que contiene los bytes menos significativos del valor.</span><span class="sxs-lookup"><span data-stu-id="e5ea6-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e5ea6-108">[in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e5ea6-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e5ea6-109">[in] Un `PCCOR_SIGNATURE` valor al que apunta a la firma de metadatos binaria del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="e5ea6-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e5ea6-110">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en la ubicación especificada del registro y la memoria.</span><span class="sxs-lookup"><span data-stu-id="e5ea6-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ea6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5ea6-111">Requirements</span></span>  
 <span data-ttu-id="e5ea6-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5ea6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ea6-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5ea6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5ea6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5ea6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5ea6-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ea6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ea6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ea6-116">See also</span></span>
