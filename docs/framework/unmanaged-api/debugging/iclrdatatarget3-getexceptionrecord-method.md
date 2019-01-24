---
title: ICLRDataTarget3::GetExceptionRecord (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db48febc34514f51ffc4b2e1222af3bf652a67a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499794"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="b0d67-102">ICLRDataTarget3::GetExceptionRecord (Método)</span><span class="sxs-lookup"><span data-stu-id="b0d67-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="b0d67-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de excepciones asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="b0d67-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="b0d67-104">Por ejemplo, para un destino de volcado de memoria, esto sería equivalente al registro de excepciones que pasan a través de la `ExceptionParam` argumento para el [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) función de Windows Debug Help Library (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="b0d67-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d67-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0d67-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0d67-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0d67-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="b0d67-107">[in] Tamaño del búfer de entrada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="b0d67-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="b0d67-108">Esto debe ser igual a `sizeof(` [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`.</span><span class="sxs-lookup"><span data-stu-id="b0d67-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="b0d67-109">[out] Puntero a un tipo `ULONG32` que recibe el número de bytes escritos realmente en el búfer.</span><span class="sxs-lookup"><span data-stu-id="b0d67-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b0d67-110">[out] Puntero a un búfer de memoria que recibe una copia del registro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="b0d67-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="b0d67-111">El registro de excepciones se devuelve como un [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) tipo.</span><span class="sxs-lookup"><span data-stu-id="b0d67-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0d67-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0d67-112">Return Value</span></span>  
 <span data-ttu-id="b0d67-113">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b0d67-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="b0d67-114">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="b0d67-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="b0d67-115">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="b0d67-115">Return code</span></span>|<span data-ttu-id="b0d67-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0d67-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="b0d67-117">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0d67-117">Method succeeded.</span></span> <span data-ttu-id="b0d67-118">El registro de excepciones se ha copiado en el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="b0d67-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="b0d67-119">No hay ningún registro de excepciones asociado al destino.</span><span class="sxs-lookup"><span data-stu-id="b0d67-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="b0d67-120">El tamaño del búfer de entrada no es igual a `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="b0d67-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0d67-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0d67-121">Remarks</span></span>  
 <span data-ttu-id="b0d67-122">[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) es una estructura definida en dbghelp.h e imagehlp.h en Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="b0d67-122">[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="b0d67-123">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="b0d67-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0d67-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0d67-124">Requirements</span></span>  
 <span data-ttu-id="b0d67-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0d67-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0d67-126">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b0d67-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b0d67-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0d67-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0d67-128">**Versiones de .NET Framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0d67-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d67-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d67-129">See also</span></span>
- [<span data-ttu-id="b0d67-130">ICLRDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0d67-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="b0d67-131">GetExceptionContextRecord (método)</span><span class="sxs-lookup"><span data-stu-id="b0d67-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="b0d67-132">GetExceptionThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="b0d67-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
