---
description: 'Más información acerca de: ICLRDataTarget:: Request (método)'
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
ms.openlocfilehash: 75c400a51a2fdaf0044d85b5f483d783fae4628b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712173"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="db96e-103">ICLRDataTarget::Request (Método)</span><span class="sxs-lookup"><span data-stu-id="db96e-103">ICLRDataTarget::Request Method</span></span>

<span data-ttu-id="db96e-104">Llamado por los servicios de acceso a datos de Common Language Runtime (CLR) para solicitar una operación, tal y como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="db96e-104">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db96e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db96e-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="db96e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db96e-106">Parameters</span></span>  

 `reqCode`  
 <span data-ttu-id="db96e-107">de Definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="db96e-107">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="db96e-108">de Tamaño del búfer de entrada, que se usa para la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="db96e-108">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="db96e-109">de Búfer que contiene la solicitud.</span><span class="sxs-lookup"><span data-stu-id="db96e-109">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="db96e-110">de Tamaño del búfer de salida, que se usa para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="db96e-110">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="db96e-111">enuncia Búfer que contiene la respuesta.</span><span class="sxs-lookup"><span data-stu-id="db96e-111">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db96e-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db96e-112">Remarks</span></span>  

 <span data-ttu-id="db96e-113">El `Request` método facilita la adición de operaciones personalizadas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="db96e-113">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="db96e-114">Es decir, este método proporciona extensibilidad sin necesidad de revisar la definición de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="db96e-114">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="db96e-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="db96e-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db96e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db96e-116">Requirements</span></span>  

 <span data-ttu-id="db96e-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db96e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db96e-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="db96e-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="db96e-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db96e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db96e-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db96e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db96e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="db96e-121">See also</span></span>

- [<span data-ttu-id="db96e-122">ICLRDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db96e-122">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
