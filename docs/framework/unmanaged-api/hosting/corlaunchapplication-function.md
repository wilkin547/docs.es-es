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
ms.openlocfilehash: e01698d2d8491b2496bb664c13dca97964cd1481
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136943"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="e1f2f-102">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="e1f2f-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="e1f2f-103">Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="e1f2f-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f2f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1f2f-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e1f2f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1f2f-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="e1f2f-107">de Un valor de la enumeración [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) que especifica el tipo de host que está iniciando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="e1f2f-108">de Nombre completo de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="e1f2f-109">de El número de rutas de acceso de manifiesto para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="e1f2f-110">de Matriz de cadenas, cada una de las cuales especifica una ruta de acceso a un manifiesto de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="e1f2f-111">de El número de elementos de datos de activación para la aplicación que se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="e1f2f-112">de Matriz de cadenas, cada una de las cuales es un elemento de datos de activación para la aplicación que se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="e1f2f-113">enuncia Puntero a información sobre el proceso en el que se ha cargado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e1f2f-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1f2f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1f2f-114">Requirements</span></span>  
 <span data-ttu-id="e1f2f-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1f2f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1f2f-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e1f2f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1f2f-117">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e1f2f-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1f2f-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1f2f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f2f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1f2f-119">See also</span></span>

- [<span data-ttu-id="e1f2f-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e1f2f-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
