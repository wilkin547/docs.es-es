---
title: ICorDebugNativeFrame::GetLocalMemoryValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
ms.openlocfilehash: 92a4ee2007760024b5802208d77ca3abc81e3cf3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695678"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="81cc5-102">ICorDebugNativeFrame::GetLocalMemoryValue (Método)</span><span class="sxs-lookup"><span data-stu-id="81cc5-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>

<span data-ttu-id="81cc5-103">Obtiene el valor de un argumento o una variable local que está almacenado en la ubicación de memoria especificada para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="81cc5-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81cc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81cc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81cc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81cc5-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="81cc5-106">de `CORDB_ADDRESS` Valor que especifica la ubicación de memoria que contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="81cc5-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="81cc5-107">de Un entero que especifica el tamaño de la firma de metadatos binarios a la que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="81cc5-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="81cc5-108">de `PCCOR_SIGNATURE` Valor que apunta a la firma de metadatos binarios del tipo del valor.</span><span class="sxs-lookup"><span data-stu-id="81cc5-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="81cc5-109">enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor recuperado que se almacena en la ubicación de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="81cc5-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81cc5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81cc5-110">Requirements</span></span>  

 <span data-ttu-id="81cc5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81cc5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81cc5-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81cc5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81cc5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81cc5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81cc5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81cc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81cc5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81cc5-115">See also</span></span>
