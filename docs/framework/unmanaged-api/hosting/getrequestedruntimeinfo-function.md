---
title: GetRequestedRuntimeInfo (Función)
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21b96d435bdb0265d31972edbd4038d0b8cd8d2b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490344"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="7159d-102">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="7159d-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="7159d-103">Obtiene información de versión y directorio sobre requerido por una aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7159d-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="7159d-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7159d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7159d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7159d-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7159d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7159d-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="7159d-107">[in] El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7159d-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="7159d-108">[in] Cadena que especifica el número de versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7159d-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="7159d-109">[in] El nombre del archivo de configuración que está asociado con `pExe`.</span><span class="sxs-lookup"><span data-stu-id="7159d-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="7159d-110">[in] Uno o varios de los [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="7159d-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="7159d-111">[in] Uno o varios de los [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="7159d-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="7159d-112">[out] Un búfer que contiene la ruta de acceso de directorio para el tiempo de ejecución una vez finalizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7159d-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="7159d-113">[in] La longitud del búfer de directorio.</span><span class="sxs-lookup"><span data-stu-id="7159d-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="7159d-114">[out] Un puntero a la longitud de la cadena de ruta de acceso de directorio.</span><span class="sxs-lookup"><span data-stu-id="7159d-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="7159d-115">[out] Un búfer que contiene el número de versión del tiempo de ejecución una vez finalizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7159d-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7159d-116">[in] La longitud del búfer de cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="7159d-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="7159d-117">[out] Un puntero a la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="7159d-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7159d-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7159d-118">Return Value</span></span>  
 <span data-ttu-id="7159d-119">Este método devuelve códigos de error de modelo de objetos componentes (COM) estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="7159d-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="7159d-120">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="7159d-120">Return code</span></span>|<span data-ttu-id="7159d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7159d-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7159d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7159d-122">S_OK</span></span>|<span data-ttu-id="7159d-123">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7159d-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="7159d-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7159d-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7159d-125">El búfer de directorio no es suficientemente grande como para almacenar la ruta de acceso de directorio.</span><span class="sxs-lookup"><span data-stu-id="7159d-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="7159d-126">o bien</span><span class="sxs-lookup"><span data-stu-id="7159d-126">- or -</span></span><br /><br /> <span data-ttu-id="7159d-127">El búfer de versión no es suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="7159d-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7159d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7159d-128">Remarks</span></span>  
 <span data-ttu-id="7159d-129">El `GetRequestedRuntimeInfo` método devuelve información de tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la última versión instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7159d-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="7159d-130">En la versión 2.0 de .NET Framework, puede obtener información acerca de la última versión instalada mediante la `GetRequestedRuntimeInfo` método como sigue:</span><span class="sxs-lookup"><span data-stu-id="7159d-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="7159d-131">Especifique el `pExe`, `pwszVersion`, y `pConfigurationFile` parámetros como null.</span><span class="sxs-lookup"><span data-stu-id="7159d-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="7159d-132">Especifique el marcador RUNTIME_INFO_UPGRADE_VERSION en el `RUNTIME_INFO_FLAGS` enumeraciones para el `runtimeInfoFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="7159d-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="7159d-133">El `GetRequestedRuntimeInfo` método no devuelve la última versión CLR en las circunstancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="7159d-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="7159d-134">Existe un archivo de configuración que especifica la carga de una determinada versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="7159d-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="7159d-135">Tenga en cuenta que .NET Framework usará el archivo de configuración incluso si se especifica null para el `pConfigurationFile` parámetro.</span><span class="sxs-lookup"><span data-stu-id="7159d-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="7159d-136">El [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) se llamó al método especificando una versión anterior de CLR.</span><span class="sxs-lookup"><span data-stu-id="7159d-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="7159d-137">Una aplicación que se compiló para una versión anterior de CLR se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7159d-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="7159d-138">Para el `runtimeInfoFlags` parámetro, puede especificar solo una de las constantes de arquitectura de la `RUNTIME_INFO_FLAGS` enumeración al mismo tiempo:</span><span class="sxs-lookup"><span data-stu-id="7159d-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="7159d-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="7159d-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="7159d-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="7159d-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="7159d-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="7159d-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7159d-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7159d-142">Requirements</span></span>  
 <span data-ttu-id="7159d-143">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7159d-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7159d-144">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7159d-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7159d-145">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7159d-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7159d-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7159d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7159d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="7159d-147">See also</span></span>

- [<span data-ttu-id="7159d-148">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="7159d-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="7159d-149">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="7159d-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="7159d-150">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="7159d-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
