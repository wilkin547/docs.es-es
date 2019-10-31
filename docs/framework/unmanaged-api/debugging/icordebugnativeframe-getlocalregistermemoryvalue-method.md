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
ms.openlocfilehash: d44d7c23f88f5ea93f608d06b69f69b2c3637b5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096845"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="dea11-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue (Método)</span><span class="sxs-lookup"><span data-stu-id="dea11-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="dea11-103">Obtiene el valor de un argumento o una variable local, de la que la palabra baja y la palabra alta se almacenan en la ubicación de memoria y el registro especificado, respectivamente, para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="dea11-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dea11-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dea11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dea11-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dea11-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="dea11-106">de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene la palabra alta del valor.</span><span class="sxs-lookup"><span data-stu-id="dea11-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="dea11-107">de `CORDB_ADDRESS` valor que especifica la ubicación de memoria que contiene la palabra baja del valor.</span><span class="sxs-lookup"><span data-stu-id="dea11-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="dea11-108">de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el parámetro `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="dea11-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="dea11-109">de Un valor `PCCOR_SIGNATURE` que apunta a la firma de metadatos binarios del tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="dea11-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="dea11-110">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en el registro y la ubicación de memoria especificados.</span><span class="sxs-lookup"><span data-stu-id="dea11-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dea11-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dea11-111">Requirements</span></span>  
 <span data-ttu-id="dea11-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dea11-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dea11-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dea11-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dea11-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dea11-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dea11-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea11-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea11-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dea11-116">See also</span></span>
