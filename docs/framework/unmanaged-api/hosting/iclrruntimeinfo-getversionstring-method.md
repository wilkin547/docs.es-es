---
description: 'Más información acerca de: ICLRRuntimeInfo:: GetVersionString ((método)'
title: ICLRRuntimeInfo::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: 1c7603f4e9bb1142c415ba9da7a05a52d2d5e776
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753879"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="d1731-103">ICLRRuntimeInfo::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="d1731-103">ICLRRuntimeInfo::GetVersionString Method</span></span>

<span data-ttu-id="d1731-104">Obtiene la información de versión de Common Language Runtime (CLR) asociada a una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) especificada.</span><span class="sxs-lookup"><span data-stu-id="d1731-104">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="d1731-105">Este método sustituye a las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="d1731-105">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="d1731-106">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="d1731-106">GetRequestedRuntimeInfo</span></span>](getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="d1731-107">GetRequestedRuntimeVersion (</span><span class="sxs-lookup"><span data-stu-id="d1731-107">GetRequestedRuntimeVersion</span></span>](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="d1731-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1731-108">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1731-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1731-109">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="d1731-110">enuncia La versión de compilación de .NET Framework con el formato "v *A*. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="d1731-110">[out] The .NET Framework compilation version in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="d1731-111">*A*, *B* y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1731-111">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="d1731-112">*X* es opcional.</span><span class="sxs-lookup"><span data-stu-id="d1731-112">*X* is optional.</span></span> <span data-ttu-id="d1731-113">Si *X* no está presente, no hay ningún punto final.</span><span class="sxs-lookup"><span data-stu-id="d1731-113">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1731-114">Este parámetro debe coincidir con el nombre de directorio de la versión de .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="d1731-114">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="d1731-115">Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *x*", donde *x* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="d1731-115">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="d1731-116">Tenga en cuenta que el prefijo "v" es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d1731-116">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="d1731-117">[in, out] Especifica el tamaño de `pwzBuffer` para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="d1731-117">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="d1731-118">Si `pwzBuffer` es `null` , `pchBuffer` devuelve el tamaño necesario de `pwzBuffer` para permitir la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="d1731-118">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1731-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d1731-119">Return Value</span></span>  

 <span data-ttu-id="d1731-120">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d1731-120">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d1731-121">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1731-121">HRESULT</span></span>|<span data-ttu-id="d1731-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1731-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1731-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1731-123">S_OK</span></span>|<span data-ttu-id="d1731-124">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d1731-124">The method completed successfully.</span></span>|  
|<span data-ttu-id="d1731-125">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d1731-125">E_POINTER</span></span>|<span data-ttu-id="d1731-126">`pwzBuffer` o `pchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="d1731-126">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1731-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1731-127">Requirements</span></span>  

 <span data-ttu-id="d1731-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1731-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1731-129">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d1731-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d1731-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1731-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1731-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1731-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1731-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1731-132">See also</span></span>

- [<span data-ttu-id="d1731-133">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1731-133">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d1731-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d1731-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d1731-135">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="d1731-135">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="d1731-136">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d1731-136">Hosting</span></span>](index.md)
