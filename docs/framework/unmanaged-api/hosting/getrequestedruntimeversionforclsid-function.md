---
title: GetRequestedRuntimeVersionForCLSID (Función)
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b4ac1a37c2b3506216499ed0c9f8194949b768
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081897"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="b0357-102">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="b0357-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="b0357-103">Obtiene la correspondiente información common language runtime (CLR) versión para la clase con los valores especificados `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="b0357-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="b0357-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0357-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0357-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0357-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0357-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0357-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="b0357-107">[in]  El `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="b0357-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="b0357-108">[out]  Un búfer que contiene la cadena de número de versión tras completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0357-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b0357-109">[in]  El tamaño, en caracteres anchos, de la `pVersion` búfer.</span><span class="sxs-lookup"><span data-stu-id="b0357-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b0357-110">[out] La longitud, en bytes, del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="b0357-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="b0357-111">[in]  Uno de los valores CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="b0357-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="b0357-112">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b0357-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b0357-113">CLSID_RESOLUTION_DEFAULT: (0 x 0) especifica que debe usarse el comportamiento de interoperabilidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b0357-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="b0357-114">CLSID_RESOLUTION_REGISTERED: (0 x 1) especifica que se debe buscar el registro y se debe aplicar la directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b0357-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0357-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0357-115">Return Value</span></span>  
  
|<span data-ttu-id="b0357-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0357-116">HRESULT</span></span>|<span data-ttu-id="b0357-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0357-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0357-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0357-118">S_OK</span></span>|<span data-ttu-id="b0357-119">La función se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b0357-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="b0357-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0357-120">E_INVALIDARG</span></span>|<span data-ttu-id="b0357-121">Uno de los parámetros tiene un formato o tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="b0357-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="b0357-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b0357-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b0357-123">El `pVersion` búfer no es lo suficientemente grande como para contener la cadena de versión completa.</span><span class="sxs-lookup"><span data-stu-id="b0357-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="b0357-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="b0357-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="b0357-125">No hay ninguna clase registrada con los valores especificados `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="b0357-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="b0357-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b0357-126">E_POINTER</span></span>|<span data-ttu-id="b0357-127">`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es null.</span><span class="sxs-lookup"><span data-stu-id="b0357-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0357-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0357-128">Requirements</span></span>  
 <span data-ttu-id="b0357-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0357-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0357-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0357-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0357-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0357-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0357-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0357-132">See also</span></span>

- [<span data-ttu-id="b0357-133">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="b0357-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
