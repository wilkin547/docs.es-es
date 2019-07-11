---
title: CorLaunchApplication (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9861de733a9acb43c7e2a4b4941f9945fc5f0ba7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758372"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="22ca8-102">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="22ca8-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="22ca8-103">Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="22ca8-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="22ca8-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="22ca8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ca8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22ca8-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="22ca8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22ca8-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="22ca8-107">[in] Un valor de la [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeración que especifica el tipo de host que está iniciando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22ca8-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="22ca8-108">[in] El nombre completo de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="22ca8-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="22ca8-109">[in] El número de rutas de acceso de manifiesto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22ca8-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="22ca8-110">[in] Una matriz de cadenas, cada uno de los cuales especifica una ruta de acceso para un manifiesto de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="22ca8-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="22ca8-111">[in] El número de elementos de datos de activación para la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="22ca8-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="22ca8-112">[in] Una matriz de cadenas, cada uno de los cuales es un elemento de datos de activación para la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="22ca8-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="22ca8-113">[out] Un puntero a información sobre el proceso en el que se ha cargado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22ca8-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ca8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22ca8-114">Requirements</span></span>  
 <span data-ttu-id="22ca8-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ca8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ca8-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22ca8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22ca8-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22ca8-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22ca8-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ca8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ca8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="22ca8-119">See also</span></span>

- [<span data-ttu-id="22ca8-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="22ca8-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
