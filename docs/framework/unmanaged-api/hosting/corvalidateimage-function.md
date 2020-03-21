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
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178215"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="8a454-102">_CorValidateImage (Función)</span><span class="sxs-lookup"><span data-stu-id="8a454-102">_CorValidateImage Function</span></span>
<span data-ttu-id="8a454-103">Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez cargadas.</span><span class="sxs-lookup"><span data-stu-id="8a454-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a454-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a454-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a454-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a454-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="8a454-106">[en] Puntero a la ubicación inicial de la imagen para validarla como código administrado.</span><span class="sxs-lookup"><span data-stu-id="8a454-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="8a454-107">La imagen ya debe estar cargada en la memoria.</span><span class="sxs-lookup"><span data-stu-id="8a454-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="8a454-108">[en] El nombre de archivo de la imagen.</span><span class="sxs-lookup"><span data-stu-id="8a454-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a454-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a454-109">Return Value</span></span>  
 <span data-ttu-id="8a454-110">Esta función devuelve `E_INVALIDARG` `E_OUTOFMEMORY`los `E_UNEXPECTED`valores `E_FAIL`estándar , , , y , así como los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="8a454-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="8a454-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a454-111">Return value</span></span>|<span data-ttu-id="8a454-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a454-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="8a454-113">La imagen no es válida.</span><span class="sxs-lookup"><span data-stu-id="8a454-113">The image is invalid.</span></span> <span data-ttu-id="8a454-114">Este valor tiene el HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="8a454-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="8a454-115">La imagen es válida.</span><span class="sxs-lookup"><span data-stu-id="8a454-115">The image is valid.</span></span> <span data-ttu-id="8a454-116">Este valor tiene el HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="8a454-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a454-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a454-117">Remarks</span></span>  
 <span data-ttu-id="8a454-118">En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba si hay módulos administrados examinando el bit del directorio del descriptor COM en el encabezado de formato de archivo de objeto común (COFF).</span><span class="sxs-lookup"><span data-stu-id="8a454-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="8a454-119">Un bit de conjunto indica un módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="8a454-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="8a454-120">Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llama, `_CorValidateImage`que realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8a454-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="8a454-121">Confirma que la imagen es un módulo administrado válido.</span><span class="sxs-lookup"><span data-stu-id="8a454-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="8a454-122">Cambia el punto de entrada de la imagen a un punto de entrada en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8a454-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="8a454-123">Para las versiones de 64 bits de Windows, modifica la imagen que está en memoria transformándola de formato PE32 a PE32+.</span><span class="sxs-lookup"><span data-stu-id="8a454-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="8a454-124">Vuelve al cargador cuando se cargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="8a454-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="8a454-125">Para las imágenes ejecutables, el cargador del sistema operativo llama a la función [_CorExeMain,](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) independientemente del punto de entrada especificado en el ejecutable.</span><span class="sxs-lookup"><span data-stu-id="8a454-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="8a454-126">Para las imágenes de ensamblado DLL, el cargador llama a la función [_CorDllMain.](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)</span><span class="sxs-lookup"><span data-stu-id="8a454-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="8a454-127">`_CorExeMain`o `_CorDllMain` realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="8a454-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="8a454-128">Inicializa el CLR.</span><span class="sxs-lookup"><span data-stu-id="8a454-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="8a454-129">Busca el punto de entrada administrado desde el encabezado CLR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8a454-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="8a454-130">Comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a454-130">Begins execution.</span></span>  
  
 <span data-ttu-id="8a454-131">El cargador llama a la función [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) cuando se descargan imágenes de módulo sadministradas.</span><span class="sxs-lookup"><span data-stu-id="8a454-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="8a454-132">Sin embargo, esta función no realiza ninguna acción; simplemente regresa.</span><span class="sxs-lookup"><span data-stu-id="8a454-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a454-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a454-133">Requirements</span></span>  
 <span data-ttu-id="8a454-134">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a454-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a454-135">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a454-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a454-136">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a454-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a454-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a454-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a454-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a454-138">See also</span></span>

- [<span data-ttu-id="8a454-139">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="8a454-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
