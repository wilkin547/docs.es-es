---
title: "ICLRDataTarget3::GetExceptionContextRecord (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetContextRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c2e645222553f4000b300fa4f010ff81ff44d23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="dc3aa-102">ICLRDataTarget3::GetExceptionContextRecord (Método)</span><span class="sxs-lookup"><span data-stu-id="dc3aa-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="dc3aa-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="dc3aa-104">Por ejemplo, para un destino de volcado de memoria, esto sería equivalente al registro de contexto pasado a través de la `ExceptionParam` argumento pasado a la [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) función de Windows Debug Help Library (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="dc3aa-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc3aa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc3aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc3aa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc3aa-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="dc3aa-107">[in] Tamaño del búfer de entrada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="dc3aa-108">Debe ser suficientemente grande como para contener el registro de contexto.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="dc3aa-109">[out] Puntero a un tipo `ULONG32` que recibe el número de bytes escritos realmente en el búfer.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="dc3aa-110">[out] Puntero a un búfer de memoria que recibe una copia del registro del contexto.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="dc3aa-111">El registro de excepciones se devuelve como un [contexto](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) tipo.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-111">The exception record is returned as a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc3aa-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc3aa-112">Return Value</span></span>  
 <span data-ttu-id="dc3aa-113">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="dc3aa-114">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="dc3aa-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="dc3aa-115">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="dc3aa-115">Return code</span></span>|<span data-ttu-id="dc3aa-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc3aa-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="dc3aa-117">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-117">Method succeeded.</span></span> <span data-ttu-id="dc3aa-118">El registro de contexto se ha copiado en el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="dc3aa-119">No hay ningún registro de contexto asociado al destino.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="dc3aa-120">El tamaño del búfer de entrada no es suficientemente grande para alojar el registro de contexto.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc3aa-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc3aa-121">Remarks</span></span>  
 <span data-ttu-id="dc3aa-122">[CONTEXTO](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) es una estructura específica de la plataforma definida en encabezados proporcionados por el SDK de Windows.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-122">[CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="dc3aa-123">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="dc3aa-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc3aa-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc3aa-124">Requirements</span></span>  
 <span data-ttu-id="dc3aa-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc3aa-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc3aa-126">**Encabezado:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="dc3aa-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dc3aa-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc3aa-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc3aa-128">**Versiones de .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc3aa-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3aa-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc3aa-129">See Also</span></span>  
 [<span data-ttu-id="dc3aa-130">ICLRDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc3aa-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="dc3aa-131">GetExceptionRecord (método)</span><span class="sxs-lookup"><span data-stu-id="dc3aa-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [<span data-ttu-id="dc3aa-132">GetExceptionThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="dc3aa-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
