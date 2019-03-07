---
title: _CorValidateImage (Función)
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c6d3b50cb3589dcd98c53e1abf0ce2be144d8f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501999"
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="3246f-102">_CorValidateImage (Función)</span><span class="sxs-lookup"><span data-stu-id="3246f-102">_CorValidateImage Function</span></span>
<span data-ttu-id="3246f-103">Valida las imágenes de módulo administrado y notifica al cargador del sistema operativo después de que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="3246f-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3246f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3246f-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3246f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3246f-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="3246f-106">[in] Un puntero a la ubicación inicial de la imagen para validar como código administrado.</span><span class="sxs-lookup"><span data-stu-id="3246f-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="3246f-107">La imagen ya se debe cargar en la memoria.</span><span class="sxs-lookup"><span data-stu-id="3246f-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="3246f-108">[in] El nombre de archivo de la imagen.</span><span class="sxs-lookup"><span data-stu-id="3246f-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3246f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3246f-109">Return Value</span></span>  
 <span data-ttu-id="3246f-110">Esta función devuelve los valores estándar `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, y `E_FAIL`, así como los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="3246f-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="3246f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3246f-111">Return value</span></span>|<span data-ttu-id="3246f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3246f-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="3246f-113">La imagen no es válida.</span><span class="sxs-lookup"><span data-stu-id="3246f-113">The image is invalid.</span></span> <span data-ttu-id="3246f-114">Este valor tiene el resultado HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="3246f-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="3246f-115">La imagen es válida.</span><span class="sxs-lookup"><span data-stu-id="3246f-115">The image is valid.</span></span> <span data-ttu-id="3246f-116">Este valor tiene el resultado HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="3246f-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3246f-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3246f-117">Remarks</span></span>  
 <span data-ttu-id="3246f-118">En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba los módulos administrados examinando el bit de directorio de Descriptor de COM en el encabezado de common object file format (COFF).</span><span class="sxs-lookup"><span data-stu-id="3246f-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="3246f-119">Un bit establecido indica un módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="3246f-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="3246f-120">Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llamadas `_CorValidateImage`, que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3246f-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="3246f-121">Confirma que la imagen es un módulo administrado válido.</span><span class="sxs-lookup"><span data-stu-id="3246f-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="3246f-122">Cambia el punto de entrada en la imagen a un punto de entrada en common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3246f-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="3246f-123">Para las versiones de 64 bits de Windows, modifica la imagen que está en la memoria transformando PE32 en PE32 + formato.</span><span class="sxs-lookup"><span data-stu-id="3246f-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="3246f-124">Devuelve al cargador cuándo se cargan las imágenes de módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="3246f-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="3246f-125">Para las imágenes ejecutables, el cargador del sistema operativo, a continuación, llama a la [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) función, independientemente del punto de entrada especificado en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="3246f-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="3246f-126">Para las imágenes de ensamblado DLL, el cargador llama a la [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="3246f-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="3246f-127">`_CorExeMain` o `_CorDllMain` realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3246f-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="3246f-128">Inicializa el CLR.</span><span class="sxs-lookup"><span data-stu-id="3246f-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="3246f-129">Busca el punto de entrada administrado desde el encabezado CLR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3246f-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="3246f-130">Empieza a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="3246f-130">Begins execution.</span></span>  
  
 <span data-ttu-id="3246f-131">Las llamadas de cargador la [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) funcionando cuando administra las imágenes de módulo se descargan.</span><span class="sxs-lookup"><span data-stu-id="3246f-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="3246f-132">Sin embargo, esta función no realiza ninguna acción; simplemente devuelve.</span><span class="sxs-lookup"><span data-stu-id="3246f-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3246f-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3246f-133">Requirements</span></span>  
 <span data-ttu-id="3246f-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3246f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3246f-135">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3246f-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3246f-136">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3246f-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3246f-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3246f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3246f-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="3246f-138">See also</span></span>
- [<span data-ttu-id="3246f-139">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="3246f-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
