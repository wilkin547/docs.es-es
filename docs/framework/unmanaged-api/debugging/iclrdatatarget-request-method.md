---
title: "ICLRDataTarget::Request (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e7bde3a0bc26a6bc93124fa835c4203cd596906
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="eb1aa-102">ICLRDataTarget::Request (Método)</span><span class="sxs-lookup"><span data-stu-id="eb1aa-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="eb1aa-103">Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, tal como se define por la implementación.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb1aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb1aa-104">Syntax</span></span>  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb1aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb1aa-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="eb1aa-106">[in] Definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="eb1aa-107">[in] El tamaño del búfer de entrada, que se utiliza para la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="eb1aa-108">[in] Un búfer que contiene la solicitud.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="eb1aa-109">[in] El tamaño del búfer de salida, que se utiliza para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="eb1aa-110">[out] Un búfer que contiene la respuesta.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb1aa-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb1aa-111">Remarks</span></span>  
 <span data-ttu-id="eb1aa-112">El `Request` método facilita la adición de las operaciones personalizadas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="eb1aa-113">Es decir, este método proporciona extensibilidad sin necesidad de revisión de la definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="eb1aa-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="eb1aa-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb1aa-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb1aa-115">Requirements</span></span>  
 <span data-ttu-id="eb1aa-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb1aa-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb1aa-117">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="eb1aa-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="eb1aa-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb1aa-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb1aa-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb1aa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1aa-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb1aa-120">See Also</span></span>  
 [<span data-ttu-id="eb1aa-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb1aa-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
