---
description: 'Más información acerca de: ICLRMetaHost:: Getversionfromfile ((método)'
title: ICLRMetaHost::GetVersionFromFile (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
ms.openlocfilehash: 0122c4aba3b8454a84540b22e815c61a2cb25df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689058"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="f15c6-103">ICLRMetaHost::GetVersionFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="f15c6-103">ICLRMetaHost::GetVersionFromFile Method</span></span>

<span data-ttu-id="f15c6-104">Obtiene la versión de compilación .NET Framework original de un ensamblado (almacenada en los metadatos), dada su ruta de acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="f15c6-104">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="f15c6-105">Este método reemplaza a la función [GetFileVersion (](getfileversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f15c6-105">This method supersedes the [GetFileVersion](getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15c6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f15c6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f15c6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f15c6-107">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="f15c6-108">de Ruta de acceso completa del archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f15c6-108">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="f15c6-109">enuncia La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v *A*. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="f15c6-109">[out] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="f15c6-110">*A*, *B* y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="f15c6-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="f15c6-111">La longitud de esta cadena se limita a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="f15c6-111">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f15c6-112">Esta salida coincide con el nombre de directorio para la versión .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="f15c6-112">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="f15c6-113">Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="f15c6-113">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="f15c6-114">Tenga en cuenta que el prefijo "v" es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f15c6-114">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="f15c6-115">[in, out] Tamaño de `pwzbuffer` para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="f15c6-115">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f15c6-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f15c6-116">Return Value</span></span>  

 <span data-ttu-id="f15c6-117">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f15c6-117">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f15c6-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f15c6-118">HRESULT</span></span>|<span data-ttu-id="f15c6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f15c6-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f15c6-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="f15c6-120">S_OK</span></span>|<span data-ttu-id="f15c6-121">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f15c6-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="f15c6-122">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f15c6-122">E_POINTER</span></span>|<span data-ttu-id="f15c6-123">`pwzbuffer` o `pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="f15c6-123">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="f15c6-124">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="f15c6-124">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="f15c6-125">El búfer es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="f15c6-125">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f15c6-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f15c6-126">Requirements</span></span>  

 <span data-ttu-id="f15c6-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f15c6-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f15c6-128">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f15c6-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f15c6-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f15c6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f15c6-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f15c6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15c6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f15c6-131">See also</span></span>

- [<span data-ttu-id="f15c6-132">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f15c6-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="f15c6-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="f15c6-133">Hosting</span></span>](index.md)
