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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136318"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="4123a-102">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="4123a-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="4123a-103">Obtiene información de la versión y del directorio sobre el Common Language Runtime (CLR) solicitado por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4123a-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="4123a-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4123a-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4123a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4123a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4123a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4123a-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="4123a-107">de El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4123a-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="4123a-108">de Cadena que especifica el número de versión del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4123a-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="4123a-109">de Nombre del archivo de configuración asociado a `pExe`.</span><span class="sxs-lookup"><span data-stu-id="4123a-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="4123a-110">de Uno o varios de los valores de la enumeración [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4123a-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="4123a-111">de Uno o varios de los valores de la enumeración [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4123a-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="4123a-112">enuncia Un búfer que contiene la ruta de acceso al directorio al tiempo de ejecución cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="4123a-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="4123a-113">de Longitud del búfer de directorio.</span><span class="sxs-lookup"><span data-stu-id="4123a-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="4123a-114">enuncia Puntero a la longitud de la cadena de ruta de acceso del directorio.</span><span class="sxs-lookup"><span data-stu-id="4123a-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4123a-115">enuncia Un búfer que contiene el número de versión del motor en tiempo de ejecución cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="4123a-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4123a-116">de Longitud del búfer de cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="4123a-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="4123a-117">enuncia Puntero a la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="4123a-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4123a-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4123a-118">Return Value</span></span>  
 <span data-ttu-id="4123a-119">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="4123a-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4123a-120">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="4123a-120">Return code</span></span>|<span data-ttu-id="4123a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4123a-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4123a-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="4123a-122">S_OK</span></span>|<span data-ttu-id="4123a-123">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4123a-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="4123a-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4123a-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4123a-125">El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso al directorio.</span><span class="sxs-lookup"><span data-stu-id="4123a-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="4123a-126">O bien</span><span class="sxs-lookup"><span data-stu-id="4123a-126">- or -</span></span><br /><br /> <span data-ttu-id="4123a-127">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="4123a-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4123a-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4123a-128">Remarks</span></span>  
 <span data-ttu-id="4123a-129">El método `GetRequestedRuntimeInfo` devuelve información en tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la versión más reciente instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4123a-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="4123a-130">En la versión .NET Framework 2,0, puede obtener información sobre la última versión instalada mediante el método `GetRequestedRuntimeInfo` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4123a-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="4123a-131">Especifique los parámetros `pExe`, `pwszVersion`y `pConfigurationFile` como null.</span><span class="sxs-lookup"><span data-stu-id="4123a-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="4123a-132">Especifique la marca RUNTIME_INFO_UPGRADE_VERSION en las enumeraciones de `RUNTIME_INFO_FLAGS` para el parámetro `runtimeInfoFlags`.</span><span class="sxs-lookup"><span data-stu-id="4123a-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="4123a-133">El método `GetRequestedRuntimeInfo` no devuelve la última versión de CLR en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="4123a-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="4123a-134">Existe un archivo de configuración de la aplicación que especifica la carga de una determinada versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="4123a-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="4123a-135">Tenga en cuenta que la .NET Framework usará el archivo de configuración aunque especifique NULL para el parámetro `pConfigurationFile`.</span><span class="sxs-lookup"><span data-stu-id="4123a-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="4123a-136">Se llamó al método [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) especificando una versión anterior de CLR.</span><span class="sxs-lookup"><span data-stu-id="4123a-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="4123a-137">Se está ejecutando una aplicación que se compiló para una versión anterior de CLR.</span><span class="sxs-lookup"><span data-stu-id="4123a-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="4123a-138">En el caso del parámetro `runtimeInfoFlags`, solo puede especificar una de las constantes de la arquitectura de la enumeración `RUNTIME_INFO_FLAGS` a la vez:</span><span class="sxs-lookup"><span data-stu-id="4123a-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="4123a-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="4123a-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="4123a-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="4123a-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="4123a-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="4123a-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4123a-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4123a-142">Requirements</span></span>  
 <span data-ttu-id="4123a-143">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4123a-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4123a-144">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4123a-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4123a-145">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4123a-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4123a-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4123a-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4123a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="4123a-147">See also</span></span>

- [<span data-ttu-id="4123a-148">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="4123a-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="4123a-149">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="4123a-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="4123a-150">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="4123a-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
