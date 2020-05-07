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
ms.openlocfilehash: 7bbb49dc6ee9b1d29dd61ccdcfdacb62740133ed
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860265"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="5203d-102">ICLRDebuggingLibraryProvider::ProvideLibrary (Método)</span><span class="sxs-lookup"><span data-stu-id="5203d-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>

<span data-ttu-id="5203d-103">Obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite localizar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5203d-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>

## <a name="syntax"></a><span data-ttu-id="5203d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5203d-104">Syntax</span></span>

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a><span data-ttu-id="5203d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5203d-105">Parameters</span></span>

`pwszFilename` \
<span data-ttu-id="5203d-106">de Nombre del módulo que se está solicitando.</span><span class="sxs-lookup"><span data-stu-id="5203d-106">[in] The name of the module being requested.</span></span>

`dwTimestamp` \
<span data-ttu-id="5203d-107">de Marca de fecha y hora almacenada en el encabezado de archivo COFF de archivos PE.</span><span class="sxs-lookup"><span data-stu-id="5203d-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>

`pLibraryProvider` \
<span data-ttu-id="5203d-108">de El `SizeOfImage` campo almacenado en el encabezado de archivo COFF opcional de los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="5203d-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>

`hModule` \
<span data-ttu-id="5203d-109">enuncia Identificador del módulo solicitado.</span><span class="sxs-lookup"><span data-stu-id="5203d-109">[out] The handle to the requested module.</span></span>

## <a name="return-value"></a><span data-ttu-id="5203d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5203d-110">Return Value</span></span>

<span data-ttu-id="5203d-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="5203d-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="5203d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5203d-112">HRESULT</span></span>|<span data-ttu-id="5203d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5203d-113">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="5203d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5203d-114">S_OK</span></span>|<span data-ttu-id="5203d-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5203d-115">The method completed successfully.</span></span>|

## <a name="exceptions"></a><span data-ttu-id="5203d-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="5203d-116">Exceptions</span></span>

## <a name="remarks"></a><span data-ttu-id="5203d-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5203d-117">Remarks</span></span>

<span data-ttu-id="5203d-118">`ProvideLibrary`permite al depurador proporcionar los módulos necesarios para depurar archivos CLR específicos como mscordbi. dll y mscordacwks. dll.</span><span class="sxs-lookup"><span data-stu-id="5203d-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="5203d-119">Los identificadores de módulo deben seguir siendo válidos hasta que una llamada al método [ICLRDebugging:: canunloadnow (](iclrdebugging-canunloadnow-method.md) indica que se pueden liberar, momento en el que es responsabilidad del llamador liberar los identificadores.</span><span class="sxs-lookup"><span data-stu-id="5203d-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>

<span data-ttu-id="5203d-120">El depurador puede utilizar cualquier medio disponible para buscar o adquirir el módulo de depuración.</span><span class="sxs-lookup"><span data-stu-id="5203d-120">The debugger may use any available means to locate or procure the debugging module.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5203d-121">Esta característica permite al llamador de la API proporcionar módulos que contienen código ejecutable y posiblemente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="5203d-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="5203d-122">Como medida de seguridad, el autor de la llamada no debe `ProvideLibrary` usar para distribuir ningún código que no esté dispuesto a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="5203d-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>
>
> <span data-ttu-id="5203d-123">Si se detecta un problema de seguridad grave en una biblioteca ya publicada, como mscordbi. dll o mscordacwks. dll, se pueden aplicar revisiones a las correcciones de compatibilidad para reconocer las versiones incorrectas de los archivos.</span><span class="sxs-lookup"><span data-stu-id="5203d-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="5203d-124">A continuación, la corrección de compatibilidad puede emitir solicitudes para las versiones revisadas de los archivos y rechazar las versiones incorrectas Si se proporcionan como respuesta a cualquier solicitud.</span><span class="sxs-lookup"><span data-stu-id="5203d-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="5203d-125">Esto solo puede ocurrir si el usuario ha revisado una nueva versión de la corrección de compatibilidad (shim).</span><span class="sxs-lookup"><span data-stu-id="5203d-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="5203d-126">Las versiones sin revisar seguirán siendo vulnerables.</span><span class="sxs-lookup"><span data-stu-id="5203d-126">Unpatched versions will remain vulnerable.</span></span>

## <a name="requirements"></a><span data-ttu-id="5203d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5203d-127">Requirements</span></span>

<span data-ttu-id="5203d-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5203d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="5203d-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5203d-129">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="5203d-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5203d-130">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5203d-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5203d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5203d-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5203d-132">See also</span></span>

- [<span data-ttu-id="5203d-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5203d-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5203d-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="5203d-134">Debugging</span></span>](index.md)
