---
description: 'Más información acerca de: ICorDebugNativeFrame:: GetLocalRegisterMemoryValue ((método)'
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
ms.openlocfilehash: 36cf4d38c65e233a8be91a1e2aeca01ea009f340
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729190"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="80e6c-103">ICorDebugNativeFrame::GetLocalRegisterMemoryValue (Método)</span><span class="sxs-lookup"><span data-stu-id="80e6c-103">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>

<span data-ttu-id="80e6c-104">Obtiene el valor de un argumento o una variable local, de la que la palabra baja y la palabra alta se almacenan en la ubicación de memoria y el registro especificado, respectivamente, para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="80e6c-104">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80e6c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80e6c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80e6c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80e6c-106">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="80e6c-107">de Un valor de la enumeración "CorDebugRegister (" que especifica el registro que contiene la palabra alta del valor.</span><span class="sxs-lookup"><span data-stu-id="80e6c-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="80e6c-108">de `CORDB_ADDRESS` Valor que especifica la ubicación de memoria que contiene la palabra baja del valor.</span><span class="sxs-lookup"><span data-stu-id="80e6c-108">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="80e6c-109">de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="80e6c-109">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="80e6c-110">de `PCCOR_SIGNATURE` Valor que apunta a la firma de metadatos binarios del tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="80e6c-110">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="80e6c-111">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en el registro y la ubicación de memoria especificados.</span><span class="sxs-lookup"><span data-stu-id="80e6c-111">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80e6c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80e6c-112">Requirements</span></span>  

 <span data-ttu-id="80e6c-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80e6c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80e6c-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80e6c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80e6c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80e6c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80e6c-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80e6c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80e6c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="80e6c-117">See also</span></span>
