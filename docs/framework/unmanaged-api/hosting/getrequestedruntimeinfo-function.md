---
description: 'Más información acerca de: GetRequestedRuntimeInfo (función)'
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
ms.openlocfilehash: 63d0bdcd07be5727cddc0acc352e8358b5ff0090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785294"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="3af88-103">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="3af88-103">GetRequestedRuntimeInfo Function</span></span>

<span data-ttu-id="3af88-104">Obtiene información de la versión y del directorio sobre el Common Language Runtime (CLR) solicitado por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3af88-104">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="3af88-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3af88-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af88-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3af88-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3af88-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3af88-107">Parameters</span></span>  

 `pExe`  
 <span data-ttu-id="3af88-108">de El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3af88-108">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="3af88-109">de Cadena que especifica el número de versión del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3af88-109">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="3af88-110">de Nombre del archivo de configuración que está asociado a `pExe` .</span><span class="sxs-lookup"><span data-stu-id="3af88-110">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="3af88-111">de Uno o varios de los valores de enumeración de [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3af88-111">[in] One or more of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="3af88-112">de Uno o varios de los valores de enumeración de [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3af88-112">[in] One or more of the [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="3af88-113">enuncia Un búfer que contiene la ruta de acceso al directorio al tiempo de ejecución cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="3af88-113">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="3af88-114">de Longitud del búfer de directorio.</span><span class="sxs-lookup"><span data-stu-id="3af88-114">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="3af88-115">enuncia Puntero a la longitud de la cadena de ruta de acceso del directorio.</span><span class="sxs-lookup"><span data-stu-id="3af88-115">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="3af88-116">enuncia Un búfer que contiene el número de versión del motor en tiempo de ejecución cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="3af88-116">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3af88-117">de Longitud del búfer de cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="3af88-117">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="3af88-118">enuncia Puntero a la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="3af88-118">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3af88-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3af88-119">Return Value</span></span>  

 <span data-ttu-id="3af88-120">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="3af88-120">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3af88-121">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="3af88-121">Return code</span></span>|<span data-ttu-id="3af88-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3af88-122">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3af88-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="3af88-123">S_OK</span></span>|<span data-ttu-id="3af88-124">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3af88-124">The method completed successfully.</span></span>|  
|<span data-ttu-id="3af88-125">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3af88-125">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3af88-126">El búfer de directorio no es lo suficientemente grande como para almacenar la ruta de acceso al directorio.</span><span class="sxs-lookup"><span data-stu-id="3af88-126">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="3af88-127">o bien</span><span class="sxs-lookup"><span data-stu-id="3af88-127">- or -</span></span><br /><br /> <span data-ttu-id="3af88-128">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="3af88-128">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3af88-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3af88-129">Remarks</span></span>  

 <span data-ttu-id="3af88-130">El `GetRequestedRuntimeInfo` método devuelve información en tiempo de ejecución sobre la versión cargada en el proceso, que no es necesariamente la versión más reciente instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3af88-130">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="3af88-131">En la versión .NET Framework 2,0, puede obtener información sobre la última versión instalada mediante el método de la `GetRequestedRuntimeInfo` siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3af88-131">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="3af88-132">Especifique los `pExe` `pwszVersion` parámetros, y `pConfigurationFile` como null.</span><span class="sxs-lookup"><span data-stu-id="3af88-132">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="3af88-133">Especifique el marcador de RUNTIME_INFO_UPGRADE_VERSION en las `RUNTIME_INFO_FLAGS` enumeraciones para el `runtimeInfoFlags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3af88-133">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="3af88-134">El `GetRequestedRuntimeInfo` método no devuelve la última versión de CLR en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="3af88-134">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="3af88-135">Existe un archivo de configuración de la aplicación que especifica la carga de una determinada versión de CLR.</span><span class="sxs-lookup"><span data-stu-id="3af88-135">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="3af88-136">Tenga en cuenta que la .NET Framework usará el archivo de configuración aunque especifique NULL para el `pConfigurationFile` parámetro.</span><span class="sxs-lookup"><span data-stu-id="3af88-136">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="3af88-137">Se llamó al método [CorBindToRuntimeEx](corbindtoruntimeex-function.md) especificando una versión anterior de CLR.</span><span class="sxs-lookup"><span data-stu-id="3af88-137">The [CorBindToRuntimeEx](corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="3af88-138">Se está ejecutando una aplicación que se compiló para una versión anterior de CLR.</span><span class="sxs-lookup"><span data-stu-id="3af88-138">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="3af88-139">Para el `runtimeInfoFlags` parámetro, solo puede especificar una de las constantes de arquitectura de la `RUNTIME_INFO_FLAGS` enumeración a la vez:</span><span class="sxs-lookup"><span data-stu-id="3af88-139">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="3af88-140">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="3af88-140">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="3af88-141">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="3af88-141">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="3af88-142">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="3af88-142">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3af88-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3af88-143">Requirements</span></span>  

 <span data-ttu-id="3af88-144">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3af88-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3af88-145">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3af88-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3af88-146">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3af88-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3af88-147">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3af88-147">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af88-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="3af88-148">See also</span></span>

- [<span data-ttu-id="3af88-149">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="3af88-149">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="3af88-150">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="3af88-150">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="3af88-151">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3af88-151">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
