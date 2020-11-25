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
ms.openlocfilehash: 4d0cf22b4b0644d6b25d6b3ef884718cb9ca1e42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723797"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="e0211-102">ICLRDataTarget::Request (Método)</span><span class="sxs-lookup"><span data-stu-id="e0211-102">ICLRDataTarget::Request Method</span></span>

<span data-ttu-id="e0211-103">Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="e0211-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0211-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0211-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e0211-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0211-105">Parameters</span></span>  

 `reqCode`  
 <span data-ttu-id="e0211-106">de Definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e0211-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="e0211-107">de Tamaño del búfer de entrada, que se usa para la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="e0211-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="e0211-108">de Búfer que contiene la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e0211-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="e0211-109">de Tamaño del búfer de salida, que se usa para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e0211-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="e0211-110">enuncia Búfer que contiene la respuesta.</span><span class="sxs-lookup"><span data-stu-id="e0211-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0211-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0211-111">Remarks</span></span>  

 <span data-ttu-id="e0211-112">El `Request` método facilita la adición de operaciones personalizadas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="e0211-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="e0211-113">Es decir, este método proporciona extensibilidad sin necesidad de revisar la definición de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="e0211-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="e0211-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="e0211-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0211-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0211-115">Requirements</span></span>  

 <span data-ttu-id="e0211-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0211-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0211-117">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="e0211-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e0211-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0211-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0211-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0211-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0211-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0211-120">See also</span></span>

- [<span data-ttu-id="e0211-121">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0211-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
