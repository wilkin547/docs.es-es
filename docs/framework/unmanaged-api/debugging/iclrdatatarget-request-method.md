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
ms.openlocfilehash: 0a7e764d89dd42bcaf81da5cf6a16991b6b8a16e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793706"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="ebe17-102">ICLRDataTarget::Request (Método)</span><span class="sxs-lookup"><span data-stu-id="ebe17-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="ebe17-103">Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="ebe17-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebe17-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ebe17-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ebe17-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="ebe17-106">de Definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ebe17-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="ebe17-107">de Tamaño del búfer de entrada, que se usa para la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="ebe17-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="ebe17-108">de Búfer que contiene la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ebe17-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="ebe17-109">de Tamaño del búfer de salida, que se usa para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ebe17-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="ebe17-110">enuncia Búfer que contiene la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ebe17-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebe17-111">Notas</span><span class="sxs-lookup"><span data-stu-id="ebe17-111">Remarks</span></span>  
 <span data-ttu-id="ebe17-112">El método `Request` facilita la adición de operaciones personalizadas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="ebe17-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="ebe17-113">Es decir, este método proporciona extensibilidad sin necesidad de revisar la definición de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ebe17-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="ebe17-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="ebe17-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe17-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ebe17-115">Requirements</span></span>  
 <span data-ttu-id="ebe17-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebe17-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebe17-117">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="ebe17-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ebe17-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebe17-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebe17-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebe17-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe17-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebe17-120">See also</span></span>

- [<span data-ttu-id="ebe17-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebe17-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
