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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c838c994144307e9c87e3a4628fa80bfcdbeb59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406771"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="8626b-102">ICLRDataTarget3::GetExceptionThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="8626b-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="8626b-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para obtener el identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="8626b-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8626b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8626b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8626b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8626b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8626b-106">[out] Identificador del subproceso que inició la excepción.</span><span class="sxs-lookup"><span data-stu-id="8626b-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8626b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8626b-107">Return Value</span></span>  
 <span data-ttu-id="8626b-108">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="8626b-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="8626b-109">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="8626b-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="8626b-110">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="8626b-110">Return code</span></span>|<span data-ttu-id="8626b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8626b-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="8626b-112">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8626b-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="8626b-113">No se pudo encontrar un identificador de subproceso válido para la excepción.</span><span class="sxs-lookup"><span data-stu-id="8626b-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8626b-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8626b-114">Remarks</span></span>  
 <span data-ttu-id="8626b-115">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="8626b-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8626b-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8626b-116">Requirements</span></span>  
 <span data-ttu-id="8626b-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8626b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8626b-118">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8626b-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8626b-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8626b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8626b-120">**Versiones de .NET framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8626b-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8626b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8626b-121">See Also</span></span>  
 [<span data-ttu-id="8626b-122">ICLRDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8626b-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="8626b-123">GetExceptionContextRecord (método)</span><span class="sxs-lookup"><span data-stu-id="8626b-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="8626b-124">GetExceptionRecord (método)</span><span class="sxs-lookup"><span data-stu-id="8626b-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
