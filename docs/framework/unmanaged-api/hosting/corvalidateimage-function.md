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
ms.openlocfilehash: 2d49a40610bd0e1a7629594e245bde9eacfcc06d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687982"
---
# <a name="_corvalidateimage-function"></a><span data-ttu-id="ac2ff-102">_CorValidateImage (Función)</span><span class="sxs-lookup"><span data-stu-id="ac2ff-102">_CorValidateImage Function</span></span>

<span data-ttu-id="ac2ff-103">Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac2ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac2ff-104">Syntax</span></span>  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac2ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac2ff-105">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="ac2ff-106">de Puntero a la ubicación inicial de la imagen que se va a validar como código administrado.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="ac2ff-107">La imagen ya debe estar cargada en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="ac2ff-108">de Nombre de archivo de la imagen.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac2ff-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac2ff-109">Return Value</span></span>  

 <span data-ttu-id="ac2ff-110">Esta función devuelve los valores estándar `E_INVALIDARG` , `E_OUTOFMEMORY` , `E_UNEXPECTED` y `E_FAIL` , así como los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="ac2ff-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac2ff-111">Return value</span></span>|<span data-ttu-id="ac2ff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac2ff-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="ac2ff-113">La imagen no es válida.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-113">The image is invalid.</span></span> <span data-ttu-id="ac2ff-114">Este valor tiene HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="ac2ff-115">La imagen es válida.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-115">The image is valid.</span></span> <span data-ttu-id="ac2ff-116">Este valor tiene HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac2ff-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac2ff-117">Remarks</span></span>  

 <span data-ttu-id="ac2ff-118">En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba los módulos administrados examinando el bit del directorio de descriptores COM en el encabezado Common Object File Format (COFF).</span><span class="sxs-lookup"><span data-stu-id="ac2ff-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="ac2ff-119">Un bit establecido indica un módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="ac2ff-120">Si el cargador detecta un módulo administrado, carga MsCorEE.dll y llama a `_CorValidateImage` , que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac2ff-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
- <span data-ttu-id="ac2ff-121">Confirma que la imagen es un módulo administrado válido.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-121">Confirms that the image is a valid managed module.</span></span>  
  
- <span data-ttu-id="ac2ff-122">Cambia el punto de entrada de la imagen a un punto de entrada en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ac2ff-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
- <span data-ttu-id="ac2ff-123">En las versiones de Windows de 64 bits, modifica la imagen que está en la memoria transformando el formato de PE32 a PE32 +.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
- <span data-ttu-id="ac2ff-124">Vuelve al cargador cuando se cargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="ac2ff-125">En el caso de las imágenes ejecutables, el cargador del sistema operativo llama a la función [_CorExeMain](corexemain-function.md) , independientemente del punto de entrada especificado en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-125">For executable images, the operating system loader then calls the [_CorExeMain](corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="ac2ff-126">En el caso de las imágenes de ensamblado de DLL, el cargador llama a la función [_CorDllMain](cordllmain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="ac2ff-126">For DLL assembly images, the loader calls the [_CorDllMain](cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="ac2ff-127">`_CorExeMain` o `_CorDllMain` realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ac2ff-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
- <span data-ttu-id="ac2ff-128">Inicializa el CLR.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-128">Initializes the CLR.</span></span>  
  
- <span data-ttu-id="ac2ff-129">Busca el punto de entrada administrado del encabezado CLR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
- <span data-ttu-id="ac2ff-130">Comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-130">Begins execution.</span></span>  
  
 <span data-ttu-id="ac2ff-131">El cargador llama a la función [_CorImageUnloading](corimageunloading-function.md) cuando se descargan las imágenes del módulo administrado.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-131">The loader calls the [_CorImageUnloading](corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="ac2ff-132">Sin embargo, esta función no realiza ninguna acción; simplemente devuelve.</span><span class="sxs-lookup"><span data-stu-id="ac2ff-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac2ff-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac2ff-133">Requirements</span></span>  

 <span data-ttu-id="ac2ff-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac2ff-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac2ff-135">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ac2ff-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac2ff-136">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac2ff-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac2ff-137">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac2ff-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac2ff-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac2ff-138">See also</span></span>

- [<span data-ttu-id="ac2ff-139">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="ac2ff-139">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
