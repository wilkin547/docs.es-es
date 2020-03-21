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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178156"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="bf6fd-102">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="bf6fd-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="bf6fd-103">Obtiene información de versión y directorio sobre Common Language Runtime (CLR) solicitada por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="bf6fd-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf6fd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf6fd-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="bf6fd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf6fd-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="bf6fd-107">[en] El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="bf6fd-108">[en] Cadena que especifica el número de versión del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="bf6fd-109">[en] El nombre del archivo de `pExe`configuración asociado a .</span><span class="sxs-lookup"><span data-stu-id="bf6fd-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="bf6fd-110">[en] Uno o varios de los valores de enumeración [STARTUP_FLAGS.](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="bf6fd-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="bf6fd-111">[en] Uno o varios de los [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="bf6fd-112">[fuera] Un búfer que contiene la ruta de acceso del directorio al tiempo de ejecución una vez completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="bf6fd-113">[en] La longitud del búfer de directorio.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="bf6fd-114">[fuera] Un puntero a la longitud de la cadena de ruta de acceso del directorio.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="bf6fd-115">[fuera] Un búfer que contiene el número de versión del tiempo de ejecución una vez completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="bf6fd-116">[en] La longitud del búfer de cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="bf6fd-117">[fuera] Un puntero a la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf6fd-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf6fd-118">Return Value</span></span>  
 <span data-ttu-id="bf6fd-119">Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="bf6fd-120">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="bf6fd-120">Return code</span></span>|<span data-ttu-id="bf6fd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf6fd-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="bf6fd-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf6fd-122">S_OK</span></span>|<span data-ttu-id="bf6fd-123">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="bf6fd-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="bf6fd-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="bf6fd-125">El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso del directorio.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="bf6fd-126">O bien</span><span class="sxs-lookup"><span data-stu-id="bf6fd-126">- or -</span></span><br /><br /> <span data-ttu-id="bf6fd-127">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf6fd-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bf6fd-128">Remarks</span></span>  
 <span data-ttu-id="bf6fd-129">El `GetRequestedRuntimeInfo` método devuelve información en tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la versión más reciente instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="bf6fd-130">En la versión 2.0 de .NET Framework, puede obtener `GetRequestedRuntimeInfo` información sobre la última versión instalada mediante el método siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf6fd-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="bf6fd-131">Especifique `pExe`los `pwszVersion`parámetros , , y `pConfigurationFile` null.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="bf6fd-132">Especifique el indicador `RUNTIME_INFO_FLAGS` RUNTIME_INFO_UPGRADE_VERSION en `runtimeInfoFlags` las enumeraciones del parámetro.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="bf6fd-133">El `GetRequestedRuntimeInfo` método no devuelve la versión más reciente de CLR en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="bf6fd-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="bf6fd-134">Existe un archivo de configuración de aplicación que especifica la carga de una versión CLR determinada.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="bf6fd-135">Tenga en cuenta que .NET Framework usará el archivo `pConfigurationFile` de configuración incluso si especifica null para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="bf6fd-136">Se llamó al método [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) especificando una versión anterior de CLR.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="bf6fd-137">Una aplicación que se compiló para una versión anterior de CLR se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bf6fd-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="bf6fd-138">Para `runtimeInfoFlags` el parámetro, puede especificar solo una de `RUNTIME_INFO_FLAGS` las constantes de arquitectura de la enumeración a la vez:</span><span class="sxs-lookup"><span data-stu-id="bf6fd-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="bf6fd-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="bf6fd-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="bf6fd-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="bf6fd-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="bf6fd-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="bf6fd-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf6fd-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf6fd-142">Requirements</span></span>  
 <span data-ttu-id="bf6fd-143">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf6fd-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf6fd-144">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="bf6fd-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf6fd-145">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bf6fd-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf6fd-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf6fd-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6fd-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf6fd-147">See also</span></span>

- [<span data-ttu-id="bf6fd-148">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="bf6fd-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="bf6fd-149">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="bf6fd-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="bf6fd-150">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="bf6fd-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
