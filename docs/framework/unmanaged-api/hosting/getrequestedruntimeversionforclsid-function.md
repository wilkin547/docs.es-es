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
ms.openlocfilehash: 9dfce10c94e04dcd405e06ab6d0984e64984709e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779565"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="c6426-102">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="c6426-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="c6426-103">Obtiene la correspondiente información common language runtime (CLR) versión para la clase con los valores especificados `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="c6426-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="c6426-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c6426-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6426-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6426-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6426-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6426-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="c6426-107">[in]  El `CLSID` del componente.</span><span class="sxs-lookup"><span data-stu-id="c6426-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="c6426-108">[out]  Un búfer que contiene la cadena de número de versión tras completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6426-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c6426-109">[in]  El tamaño, en caracteres anchos, de la `pVersion` búfer.</span><span class="sxs-lookup"><span data-stu-id="c6426-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c6426-110">[out] La longitud, en bytes, del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="c6426-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="c6426-111">[in]  Uno de los valores CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="c6426-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="c6426-112">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c6426-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="c6426-113">CLSID_RESOLUTION_DEFAULT: (0 x 0) especifica que debe usarse el comportamiento de interoperabilidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c6426-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="c6426-114">CLSID_RESOLUTION_REGISTERED: (0 x 1) especifica que se debe buscar el registro y se debe aplicar la directiva de correcciones de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c6426-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6426-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c6426-115">Return Value</span></span>  
  
|<span data-ttu-id="c6426-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6426-116">HRESULT</span></span>|<span data-ttu-id="c6426-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c6426-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6426-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6426-118">S_OK</span></span>|<span data-ttu-id="c6426-119">La función se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6426-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="c6426-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c6426-120">E_INVALIDARG</span></span>|<span data-ttu-id="c6426-121">Uno de los parámetros tiene un formato o tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="c6426-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="c6426-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c6426-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c6426-123">El `pVersion` búfer no es lo suficientemente grande como para contener la cadena de versión completa.</span><span class="sxs-lookup"><span data-stu-id="c6426-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="c6426-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="c6426-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="c6426-125">No hay ninguna clase registrada con los valores especificados `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="c6426-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="c6426-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c6426-126">E_POINTER</span></span>|<span data-ttu-id="c6426-127">`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es null.</span><span class="sxs-lookup"><span data-stu-id="c6426-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6426-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6426-128">Requirements</span></span>  
 <span data-ttu-id="c6426-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6426-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6426-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6426-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6426-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6426-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6426-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6426-132">See also</span></span>

- [<span data-ttu-id="c6426-133">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c6426-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
