---
title: ICLRDebuggingLibraryProvider::ProvideLibrary (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9cac9e00c8cb6a13e2acc62b5f314b7bc0cf9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629136"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="2ee49-102">ICLRDebuggingLibraryProvider::ProvideLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="2ee49-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="2ee49-103">Obtiene a un proveedor de la biblioteca de interfaz de devolución de llamada que permite a common language runtime (CLR) específicos de la versión a bibliotecas de depuración se puede buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="2ee49-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ee49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ee49-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ee49-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ee49-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="2ee49-106">[in] El nombre del módulo que se solicita.</span><span class="sxs-lookup"><span data-stu-id="2ee49-106">[in] The name of the module being requested .</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="2ee49-107">[in] La marca de tiempo de fecha almacenada en el encabezado del archivo COFF de archivos PE.</span><span class="sxs-lookup"><span data-stu-id="2ee49-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="2ee49-108">[in] El `SizeOfImage` campo almacenada en el encabezado de archivo opcional COFF de archivos PE.</span><span class="sxs-lookup"><span data-stu-id="2ee49-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="2ee49-109">[out] El identificador de módulo solicitado.</span><span class="sxs-lookup"><span data-stu-id="2ee49-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ee49-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2ee49-110">Return Value</span></span>  
 <span data-ttu-id="2ee49-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="2ee49-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2ee49-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ee49-112">HRESULT</span></span>|<span data-ttu-id="2ee49-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ee49-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ee49-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ee49-114">S_OK</span></span>|<span data-ttu-id="2ee49-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2ee49-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2ee49-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2ee49-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ee49-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ee49-117">Remarks</span></span>  
 <span data-ttu-id="2ee49-118">`ProvideLibrary` permite al depurador proporcionar módulos que son necesarios para depurar los archivos específicos de CLR como mscordbi.dll y mscordacwks.dll.</span><span class="sxs-lookup"><span data-stu-id="2ee49-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="2ee49-119">Los identificadores de módulo tienen que siguen siendo válidas hasta que una llamada a la [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) método indica que se pueden liberar, momento en que es responsabilidad del llamante liberar los identificadores.</span><span class="sxs-lookup"><span data-stu-id="2ee49-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="2ee49-120">El depurador puede usar cualquier medio disponible para buscar u obtener el módulo de depuración.</span><span class="sxs-lookup"><span data-stu-id="2ee49-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ee49-121">Esta característica permite al llamador de API proporcionar módulos que contienen código ejecutable y posiblemente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="2ee49-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="2ee49-122">Como precaución de seguridad, el llamador no debe usar `ProvideLibrary` para distribuir cualquier código que no está dispuesto a ejecutar por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="2ee49-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="2ee49-123">Si se detecta un problema de seguridad grave en una biblioteca ya se ha publicado, por ejemplo, el archivo mscordbi.dll o mscordacwks.dll, se pueden revisar las correcciones de compatibilidad para que reconozca las versiones de los archivos incorrectas.</span><span class="sxs-lookup"><span data-stu-id="2ee49-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="2ee49-124">La corrección de compatibilidad puede emitir solicitudes para las versiones de los archivos de revisión y rechazar las versiones incorrectas si se proporcionan en respuesta a cualquier solicitud.</span><span class="sxs-lookup"><span data-stu-id="2ee49-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="2ee49-125">Esto puede ocurrir solamente si el usuario ha aplicado revisiones a una nueva versión de la corrección de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2ee49-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="2ee49-126">Las versiones sin revisiones seguirá siendo vulnerables.</span><span class="sxs-lookup"><span data-stu-id="2ee49-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ee49-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ee49-127">Requirements</span></span>  
 <span data-ttu-id="2ee49-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ee49-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ee49-129">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ee49-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ee49-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ee49-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ee49-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ee49-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee49-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ee49-132">See also</span></span>
- [<span data-ttu-id="2ee49-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2ee49-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2ee49-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="2ee49-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
