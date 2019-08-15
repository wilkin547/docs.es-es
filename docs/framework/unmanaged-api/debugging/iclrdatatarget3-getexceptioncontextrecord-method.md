---
title: ICLRDataTarget3::GetExceptionContextRecord (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07065b15f449c2bcb84df7bbdcce65d61de007ee
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038336"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="39a22-102">ICLRDataTarget3::GetExceptionContextRecord (Método)</span><span class="sxs-lookup"><span data-stu-id="39a22-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="39a22-103">Los servicios de acceso a datos de Common Language Runtime (CLR) llaman a esta función para recuperar el registro de contexto asociado con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="39a22-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="39a22-104">Por ejemplo, para un destino de volcado de memoria, esto sería equivalente al registro de contexto pasado a `ExceptionParam` través del argumento a la función [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) en la biblioteca de ayuda de depuración de Windows (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="39a22-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a22-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39a22-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39a22-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39a22-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="39a22-107">[in] Tamaño del búfer de entrada, en bytes.</span><span class="sxs-lookup"><span data-stu-id="39a22-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="39a22-108">Debe ser suficientemente grande como para contener el registro de contexto.</span><span class="sxs-lookup"><span data-stu-id="39a22-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="39a22-109">[out] Puntero a un tipo `ULONG32` que recibe el número de bytes escritos realmente en el búfer.</span><span class="sxs-lookup"><span data-stu-id="39a22-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="39a22-110">[out] Puntero a un búfer de memoria que recibe una copia del registro del contexto.</span><span class="sxs-lookup"><span data-stu-id="39a22-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="39a22-111">El registro de excepciones se devuelve como un tipo de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="39a22-111">The exception record is returned as a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39a22-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="39a22-112">Return Value</span></span>  
 <span data-ttu-id="39a22-113">El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="39a22-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="39a22-114">Entre los códigos `HRESULT` que se pueden devolver se incluyen los siguientes, entre otros:</span><span class="sxs-lookup"><span data-stu-id="39a22-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="39a22-115">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="39a22-115">Return code</span></span>|<span data-ttu-id="39a22-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="39a22-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="39a22-117">El método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="39a22-117">Method succeeded.</span></span> <span data-ttu-id="39a22-118">El registro de contexto se ha copiado en el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="39a22-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="39a22-119">No hay ningún registro de contexto asociado al destino.</span><span class="sxs-lookup"><span data-stu-id="39a22-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="39a22-120">El tamaño del búfer de entrada no es suficientemente grande para alojar el registro de contexto.</span><span class="sxs-lookup"><span data-stu-id="39a22-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39a22-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39a22-121">Remarks</span></span>  
 <span data-ttu-id="39a22-122">El [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) es una estructura específica de la plataforma que se define en los encabezados proporcionados por el Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="39a22-122">[CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="39a22-123">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="39a22-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a22-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39a22-124">Requirements</span></span>  
 <span data-ttu-id="39a22-125">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a22-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a22-126">**Encabezado**: ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="39a22-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="39a22-127">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39a22-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a22-128">**Versiones de .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="39a22-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a22-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="39a22-129">See also</span></span>

- [<span data-ttu-id="39a22-130">ICLRDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39a22-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="39a22-131">GetExceptionRecord (método)</span><span class="sxs-lookup"><span data-stu-id="39a22-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [<span data-ttu-id="39a22-132">GetExceptionThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="39a22-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
