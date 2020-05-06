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
ms.openlocfilehash: 63c92e3f34527f895552f45d43f332f778470b13
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860427"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="5d50a-102">ICLRDataTarget3::GetExceptionThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="5d50a-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="5d50a-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d50a-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d50a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d50a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d50a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d50a-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="5d50a-106">[out] Identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d50a-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d50a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d50a-107">Return Value</span></span>  
 <span data-ttu-id="5d50a-108">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="5d50a-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="5d50a-109">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="5d50a-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="5d50a-110">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="5d50a-110">Return code</span></span>|<span data-ttu-id="5d50a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d50a-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="5d50a-112">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d50a-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="5d50a-113">No se pudo encontrar un identificador de subproceso válido para la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d50a-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d50a-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d50a-114">Remarks</span></span>  
 <span data-ttu-id="5d50a-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="5d50a-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d50a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d50a-116">Requirements</span></span>  
 <span data-ttu-id="5d50a-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d50a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d50a-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="5d50a-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5d50a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d50a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d50a-120">**.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d50a-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d50a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d50a-121">See also</span></span>

- [<span data-ttu-id="5d50a-122">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d50a-122">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="5d50a-123">Método GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="5d50a-123">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="5d50a-124">Método GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="5d50a-124">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
