---
title: "CorLaunchApplication (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bf4392f7b30a5faa1cb01e24f9262260d9c6e93a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="a352c-102">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="a352c-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="a352c-103">Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a352c-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="a352c-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a352c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a352c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a352c-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a352c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a352c-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="a352c-107">[in] Un valor de la [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeración que especifica el tipo de host que está iniciando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a352c-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="a352c-108">[in] El nombre completo de la aplicación que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a352c-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="a352c-109">[in] El número de rutas de acceso de manifiestos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a352c-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="a352c-110">[in] Una matriz de cadenas, cada uno de los cuales especifica una ruta de acceso a un manifiesto de la aplicación que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a352c-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="a352c-111">[in] El número de elementos de datos de activación para la aplicación que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a352c-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="a352c-112">[in] Una matriz de cadenas, cada uno de los cuales es un elemento de datos de activación para la aplicación que se inicia.</span><span class="sxs-lookup"><span data-stu-id="a352c-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="a352c-113">[out] Puntero a información sobre el proceso en el que se ha cargado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a352c-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a352c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a352c-114">Requirements</span></span>  
 <span data-ttu-id="a352c-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a352c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a352c-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a352c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a352c-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a352c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a352c-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a352c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a352c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a352c-119">See Also</span></span>  
 [<span data-ttu-id="a352c-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="a352c-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
