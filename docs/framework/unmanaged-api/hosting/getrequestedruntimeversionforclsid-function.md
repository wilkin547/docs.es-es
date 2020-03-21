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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178118"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="b444a-102">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="b444a-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="b444a-103">Obtiene la información de versión de Common Language Runtime `CLSID`(CLR) adecuada para la clase con el archivo .</span><span class="sxs-lookup"><span data-stu-id="b444a-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="b444a-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b444a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b444a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b444a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b444a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b444a-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="b444a-107">[en]  El `CLSID` componente.</span><span class="sxs-lookup"><span data-stu-id="b444a-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="b444a-108">[fuera]  Un búfer que contiene la cadena de número de versión una vez completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b444a-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b444a-109">[en]  El tamaño, en caracteres `pVersion` anchos, del búfer.</span><span class="sxs-lookup"><span data-stu-id="b444a-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b444a-110">[fuera] La longitud, en bytes, del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="b444a-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="b444a-111">[en]  Uno de los valores CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="b444a-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="b444a-112">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="b444a-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="b444a-113">CLSID_RESOLUTION_DEFAULT: (0x0) Especifica que se debe utilizar el comportamiento de interoperabilidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b444a-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="b444a-114">CLSID_RESOLUTION_REGISTERED: (0x1) Especifica que se debe buscar en el registro y aplicar la directiva de correcciones de archivos.</span><span class="sxs-lookup"><span data-stu-id="b444a-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b444a-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b444a-115">Return Value</span></span>  
  
|<span data-ttu-id="b444a-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b444a-116">HRESULT</span></span>|<span data-ttu-id="b444a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b444a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b444a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b444a-118">S_OK</span></span>|<span data-ttu-id="b444a-119">La función se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b444a-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="b444a-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b444a-120">E_INVALIDARG</span></span>|<span data-ttu-id="b444a-121">Uno de los parámetros tiene un tipo o formato no válido.</span><span class="sxs-lookup"><span data-stu-id="b444a-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="b444a-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b444a-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b444a-123">El `pVersion` búfer no es lo suficientemente grande como para contener toda la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="b444a-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="b444a-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="b444a-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="b444a-125">No hay ninguna clase registrada `CLSID`con el archivo .</span><span class="sxs-lookup"><span data-stu-id="b444a-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="b444a-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b444a-126">E_POINTER</span></span>|<span data-ttu-id="b444a-127">`dwLength`es null, `cchBuffer` o es lo suficientemente `pVersion` grande como para contener la cadena de versión, pero es null.</span><span class="sxs-lookup"><span data-stu-id="b444a-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b444a-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b444a-128">Requirements</span></span>  
 <span data-ttu-id="b444a-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b444a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b444a-130">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="b444a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b444a-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b444a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b444a-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b444a-132">See also</span></span>

- [<span data-ttu-id="b444a-133">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="b444a-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
