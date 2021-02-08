---
description: 'Más información sobre: ICLRDataTarget3:: Getexceptionthreadid ((método)'
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
ms.openlocfilehash: 8202b6d83d0c81853111c5da7cfb8deec4d4e222
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794824"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="ba01c-103">ICLRDataTarget3::GetExceptionThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="ba01c-103">ICLRDataTarget3::GetExceptionThreadID Method</span></span>

<span data-ttu-id="ba01c-104">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="ba01c-104">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba01c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba01c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba01c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba01c-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="ba01c-107">[out] Identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="ba01c-107">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba01c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba01c-108">Return Value</span></span>  

 <span data-ttu-id="ba01c-109">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="ba01c-109">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="ba01c-110">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="ba01c-110">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="ba01c-111">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="ba01c-111">Return code</span></span>|<span data-ttu-id="ba01c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba01c-112">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba01c-113">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba01c-113">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="ba01c-114">No se pudo encontrar un identificador de subproceso válido para la excepción.</span><span class="sxs-lookup"><span data-stu-id="ba01c-114">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba01c-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba01c-115">Remarks</span></span>  

 <span data-ttu-id="ba01c-116">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="ba01c-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba01c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba01c-117">Requirements</span></span>  

 <span data-ttu-id="ba01c-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba01c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba01c-119">**Encabezado:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="ba01c-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ba01c-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba01c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba01c-121">**.NET Framework versiones:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ba01c-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba01c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba01c-122">See also</span></span>

- [<span data-ttu-id="ba01c-123">ICLRDataTarget3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba01c-123">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="ba01c-124">Método GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="ba01c-124">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="ba01c-125">Método GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="ba01c-125">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
