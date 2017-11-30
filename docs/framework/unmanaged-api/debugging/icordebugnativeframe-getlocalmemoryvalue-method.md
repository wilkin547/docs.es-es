---
title: "ICorDebugNativeFrame::GetLocalMemoryValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a43bc0b4bcfb50804e4bffbe4f4f18280f873436
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="1cc0a-102">ICorDebugNativeFrame::GetLocalMemoryValue (Método)</span><span class="sxs-lookup"><span data-stu-id="1cc0a-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="1cc0a-103">Obtiene el valor de un argumento o una variable local que se almacena en la ubicación de memoria especificada para este marco nativo.</span><span class="sxs-lookup"><span data-stu-id="1cc0a-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cc0a-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cc0a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1cc0a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1cc0a-106">[in] Un `CORDB_ADDRESS` valor que especifica la ubicación de memoria que contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="1cc0a-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1cc0a-107">[in] Un entero que especifica el tamaño de la firma de metadatos binaria que hace referencia el `pvSigBlob` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1cc0a-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1cc0a-108">[in] Un `PCCOR_SIGNATURE` valor que señala a la firma de metadatos binaria del tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="1cc0a-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1cc0a-109">[out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor recuperado que se almacena en la ubicación de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="1cc0a-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc0a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cc0a-110">Requirements</span></span>  
 <span data-ttu-id="1cc0a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc0a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc0a-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cc0a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cc0a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cc0a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cc0a-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc0a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc0a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cc0a-115">See Also</span></span>  
 
