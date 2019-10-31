---
title: ICLRDataTarget3::GetExceptionThreadID (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 5e7fd2f277a9c3d8410020a53d348456ef9deffb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111907"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="082f4-102">ICLRDataTarget3::GetExceptionThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="082f4-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="082f4-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="082f4-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="082f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="082f4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="082f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="082f4-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="082f4-106">[out] Identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="082f4-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="082f4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="082f4-107">Return Value</span></span>  
 <span data-ttu-id="082f4-108">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="082f4-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="082f4-109">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="082f4-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="082f4-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="082f4-110">Return code</span></span>|<span data-ttu-id="082f4-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="082f4-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="082f4-112">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="082f4-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="082f4-113">No se pudo encontrar un identificador de subproceso válido para la excepción.</span><span class="sxs-lookup"><span data-stu-id="082f4-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="082f4-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="082f4-114">Remarks</span></span>  
 <span data-ttu-id="082f4-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="082f4-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="082f4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="082f4-116">Requirements</span></span>  
 <span data-ttu-id="082f4-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="082f4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="082f4-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="082f4-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="082f4-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="082f4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="082f4-120">**Versiones de .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="082f4-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="082f4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="082f4-121">See also</span></span>

- [<span data-ttu-id="082f4-122">ICLRDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="082f4-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="082f4-123">GetExceptionContextRecord (método)</span><span class="sxs-lookup"><span data-stu-id="082f4-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="082f4-124">GetExceptionRecord (método)</span><span class="sxs-lookup"><span data-stu-id="082f4-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
