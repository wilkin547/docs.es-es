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
ms.openlocfilehash: 3afb89a42d7e26c5e89e6f9458ef3406cc0102ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684192"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="9219c-102">GetRequestedRuntimeVersionForCLSID (Función)</span><span class="sxs-lookup"><span data-stu-id="9219c-102">GetRequestedRuntimeVersionForCLSID Function</span></span>

<span data-ttu-id="9219c-103">Obtiene la información de versión de Common Language Runtime (CLR) adecuada para la clase con el especificado `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="9219c-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="9219c-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9219c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9219c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9219c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9219c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9219c-106">Parameters</span></span>  

 `rclsid`  
 <span data-ttu-id="9219c-107">de  `CLSID` Del componente.</span><span class="sxs-lookup"><span data-stu-id="9219c-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="9219c-108">enuncia  Un búfer que contiene la cadena del número de versión cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="9219c-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9219c-109">de  Tamaño, en caracteres anchos, del `pVersion` búfer.</span><span class="sxs-lookup"><span data-stu-id="9219c-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9219c-110">enuncia La longitud, en bytes, del búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="9219c-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="9219c-111">de  Uno de los valores de CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="9219c-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="9219c-112">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="9219c-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="9219c-113">CLSID_RESOLUTION_DEFAULT: (0X0) especifica que debe usarse el comportamiento predeterminado de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="9219c-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="9219c-114">CLSID_RESOLUTION_REGISTERED: (0x1) especifica que se debe buscar en el registro y que se aplique la Directiva de correcciones de compatibilidad (shim).</span><span class="sxs-lookup"><span data-stu-id="9219c-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9219c-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9219c-115">Return Value</span></span>  
  
|<span data-ttu-id="9219c-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9219c-116">HRESULT</span></span>|<span data-ttu-id="9219c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9219c-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9219c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="9219c-118">S_OK</span></span>|<span data-ttu-id="9219c-119">La función se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9219c-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="9219c-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9219c-120">E_INVALIDARG</span></span>|<span data-ttu-id="9219c-121">Uno de los parámetros tiene un tipo o formato no válido.</span><span class="sxs-lookup"><span data-stu-id="9219c-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="9219c-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9219c-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9219c-123">El `pVersion` búfer no es suficientemente grande para contener la cadena de versión completa.</span><span class="sxs-lookup"><span data-stu-id="9219c-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="9219c-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="9219c-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="9219c-125">No hay ninguna clase registrada con el especificado `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="9219c-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="9219c-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9219c-126">E_POINTER</span></span>|<span data-ttu-id="9219c-127">`dwLength` es null, o `cchBuffer` es lo suficientemente grande como para contener la cadena de versión, pero `pVersion` es NULL.</span><span class="sxs-lookup"><span data-stu-id="9219c-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9219c-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9219c-128">Requirements</span></span>  

 <span data-ttu-id="9219c-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9219c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9219c-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9219c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9219c-131">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9219c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9219c-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9219c-132">See also</span></span>

- [<span data-ttu-id="9219c-133">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9219c-133">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
