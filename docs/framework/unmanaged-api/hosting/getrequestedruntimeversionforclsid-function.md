---
description: 'Más información acerca de: GetRequestedRuntimeVersionForCLSID ((función)'
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
ms.openlocfilehash: 10fdc947181d3f1fa12b33f11cf31b68fc4285cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785268"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="63602-103">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="63602-103">GetRequestedRuntimeVersionForCLSID Function</span></span>

<span data-ttu-id="63602-104">Obtiene la información de versión de Common Language Runtime (CLR) adecuada para la clase con el especificado `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="63602-104">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="63602-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="63602-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63602-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63602-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63602-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63602-107">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="63602-108">de  `CLSID` Del componente.</span><span class="sxs-lookup"><span data-stu-id="63602-108">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="63602-109">enuncia  Un búfer que contiene la cadena del número de versión cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="63602-109">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="63602-110">de  Tamaño, en caracteres anchos, del `pVersion` búfer.</span><span class="sxs-lookup"><span data-stu-id="63602-110">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="63602-111">enuncia La longitud, en bytes, del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="63602-111">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="63602-112">de  Uno de los valores de CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="63602-112">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="63602-113">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="63602-113">The following values are supported:</span></span>  
  
- <span data-ttu-id="63602-114">CLSID_RESOLUTION_DEFAULT: (0X0) especifica que debe usarse el comportamiento predeterminado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="63602-114">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="63602-115">CLSID_RESOLUTION_REGISTERED: (0x1) especifica que se debe buscar en el registro y que se aplique la Directiva de correcciones de compatibilidad (shim).</span><span class="sxs-lookup"><span data-stu-id="63602-115">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63602-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63602-116">Return Value</span></span>  
  
|<span data-ttu-id="63602-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63602-117">HRESULT</span></span>|<span data-ttu-id="63602-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="63602-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63602-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="63602-119">S_OK</span></span>|<span data-ttu-id="63602-120">La función se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="63602-120">The function returned successfully.</span></span>|  
|<span data-ttu-id="63602-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="63602-121">E_INVALIDARG</span></span>|<span data-ttu-id="63602-122">Uno de los parámetros tiene un tipo o formato no válido.</span><span class="sxs-lookup"><span data-stu-id="63602-122">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="63602-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="63602-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="63602-124">El `pVersion` búfer no es suficientemente grande para contener la cadena de versión completa.</span><span class="sxs-lookup"><span data-stu-id="63602-124">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="63602-125">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="63602-125">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="63602-126">No hay ninguna clase registrada con el especificado `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="63602-126">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="63602-127">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="63602-127">E_POINTER</span></span>|<span data-ttu-id="63602-128">`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es NULL.</span><span class="sxs-lookup"><span data-stu-id="63602-128">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63602-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63602-129">Requirements</span></span>  

 <span data-ttu-id="63602-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63602-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63602-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="63602-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63602-132">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63602-132">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63602-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="63602-133">See also</span></span>

- [<span data-ttu-id="63602-134">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="63602-134">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
