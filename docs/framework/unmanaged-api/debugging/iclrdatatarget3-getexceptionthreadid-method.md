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
ms.openlocfilehash: 0a8b7a90cd909379f870f6a501a940386d2e1451
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723602"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="bc884-102">ICLRDataTarget3::GetExceptionThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="bc884-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>

<span data-ttu-id="bc884-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="bc884-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc884-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc884-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc884-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc884-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="bc884-106">[out] Identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="bc884-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc884-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bc884-107">Return Value</span></span>  

 <span data-ttu-id="bc884-108">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="bc884-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="bc884-109">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="bc884-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="bc884-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="bc884-110">Return code</span></span>|<span data-ttu-id="bc884-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc884-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="bc884-112">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bc884-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="bc884-113">No se pudo encontrar un identificador de subproceso válido para la excepción.</span><span class="sxs-lookup"><span data-stu-id="bc884-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc884-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc884-114">Remarks</span></span>  

 <span data-ttu-id="bc884-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="bc884-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc884-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc884-116">Requirements</span></span>  

 <span data-ttu-id="bc884-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc884-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc884-118">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="bc884-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bc884-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc884-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc884-120">**.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bc884-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc884-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc884-121">See also</span></span>

- [<span data-ttu-id="bc884-122">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc884-122">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="bc884-123">Método GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="bc884-123">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="bc884-124">Método GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="bc884-124">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
