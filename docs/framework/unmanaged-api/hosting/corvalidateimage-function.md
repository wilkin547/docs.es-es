---
description: 'Más información acerca de: _CorValidateImage función'
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
ms.openlocfilehash: f3d91c2d7e05786f7bfb0ab94b64e2cfb84a21d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746248"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="0d619-103">_CorValidateImage (Función)</span><span class="sxs-lookup"><span data-stu-id="0d619-103">_CorValidateImage Function</span></span>

<span data-ttu-id="0d619-104">Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="0d619-104">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d619-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d619-105">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d619-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d619-106">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="0d619-107">de Puntero a la ubicación inicial de la imagen que se va a validar como código administrado.</span><span class="sxs-lookup"><span data-stu-id="0d619-107">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="0d619-108">La imagen ya debe estar cargada en la memoria.</span><span class="sxs-lookup"><span data-stu-id="0d619-108">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="0d619-109">de Nombre de archivo de la imagen.</span><span class="sxs-lookup"><span data-stu-id="0d619-109">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d619-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d619-110">Return Value</span></span>  

 <span data-ttu-id="0d619-111">Esta función devuelve los valores estándar `E_INVALIDARG` , `E_OUTOFMEMORY` , `E_UNEXPECTED` y `E_FAIL` , así como los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="0d619-111">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="0d619-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d619-112">Return value</span></span>|<span data-ttu-id="0d619-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d619-113">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="0d619-114">La imagen no es válida.</span><span class="sxs-lookup"><span data-stu-id="0d619-114">The image is invalid.</span></span> <span data-ttu-id="0d619-115">Este valor tiene HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="0d619-115">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="0d619-116">La imagen es válida.</span><span class="sxs-lookup"><span data-stu-id="0d619-116">The image is valid.</span></span> <span data-ttu-id="0d619-117">Este valor tiene HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="0d619-117">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d619-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d619-118">Remarks</span></span>  

 <span data-ttu-id="0d619-119">En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba los módulos administrados examinando el bit del directorio de descriptores COM en el encabezado Common Object File Format (COFF).</span><span class="sxs-lookup"><span data-stu-id="0d619-119">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="0d619-120">Un bit establecido indica un módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="0d619-120">A set bit indicates a managed module.</span></span> <span data-ttu-id="0d619-121">Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llama a `_CorValidateImage` , que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0d619-121">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="0d619-122">Confirma que la imagen es un módulo administrado válido.</span><span class="sxs-lookup"><span data-stu-id="0d619-122">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="0d619-123">Cambia el punto de entrada de la imagen a un punto de entrada en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0d619-123">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="0d619-124">En las versiones de Windows de 64 bits, modifica la imagen que está en la memoria transformando el formato de PE32 a PE32 +.</span><span class="sxs-lookup"><span data-stu-id="0d619-124">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="0d619-125">Vuelve al cargador cuando se cargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="0d619-125">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="0d619-126">En el caso de las imágenes ejecutables, el cargador del sistema operativo llama a la función [_CorExeMain](corexemain-function.md) , independientemente del punto de entrada especificado en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="0d619-126">For executable images, the operating system loader then calls the [_CorExeMain](corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="0d619-127">En el caso de las imágenes de ensamblado de DLL, el cargador llama a la función [_CorDllMain](cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0d619-127">For DLL assembly images, the loader calls the [_CorDllMain](cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="0d619-128">`_CorExeMain` o `_CorDllMain` realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0d619-128">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="0d619-129">Inicializa el CLR.</span><span class="sxs-lookup"><span data-stu-id="0d619-129">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="0d619-130">Busca el punto de entrada administrado del encabezado CLR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d619-130">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="0d619-131">Comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0d619-131">Begins execution.</span></span>  
  
 <span data-ttu-id="0d619-132">El cargador llama a la función [_CorImageUnloading](corimageunloading-function.md) cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="0d619-132">The loader calls the [_CorImageUnloading](corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="0d619-133">Sin embargo, esta función no realiza ninguna acción; simplemente devuelve.</span><span class="sxs-lookup"><span data-stu-id="0d619-133">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d619-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d619-134">Requirements</span></span>  

 <span data-ttu-id="0d619-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d619-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d619-136">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0d619-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d619-137">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d619-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d619-138">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d619-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d619-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d619-139">See also</span></span>

- [<span data-ttu-id="0d619-140">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="0d619-140">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
