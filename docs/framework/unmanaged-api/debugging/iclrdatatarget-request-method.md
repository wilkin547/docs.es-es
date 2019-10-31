---
title: ICLRDataTarget::Request (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: e5d7a6b9826a734363d6beeb2e3fab8422964558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113348"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="e82c9-102">ICLRDataTarget::Request (Método)</span><span class="sxs-lookup"><span data-stu-id="e82c9-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="e82c9-103">Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="e82c9-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e82c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e82c9-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="e82c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e82c9-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="e82c9-106">de Definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e82c9-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="e82c9-107">de Tamaño del búfer de entrada, que se usa para la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="e82c9-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="e82c9-108">de Búfer que contiene la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e82c9-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="e82c9-109">de Tamaño del búfer de salida, que se usa para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e82c9-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="e82c9-110">enuncia Búfer que contiene la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e82c9-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e82c9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e82c9-111">Remarks</span></span>  
 <span data-ttu-id="e82c9-112">El método `Request` facilita la adición de operaciones personalizadas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="e82c9-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="e82c9-113">Es decir, este método proporciona extensibilidad sin necesidad de revisar la definición de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="e82c9-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="e82c9-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="e82c9-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e82c9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e82c9-115">Requirements</span></span>  
 <span data-ttu-id="e82c9-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e82c9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e82c9-117">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="e82c9-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e82c9-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e82c9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e82c9-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e82c9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82c9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e82c9-120">See also</span></span>

- [<span data-ttu-id="e82c9-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e82c9-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
