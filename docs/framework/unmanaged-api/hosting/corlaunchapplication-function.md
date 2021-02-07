---
description: 'Más información acerca de: CorLaunchApplication ((función)'
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
ms.openlocfilehash: 89f1f37ddde69fb5ecc24fd9dfd0d0c27d5fac40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716957"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="71b34-103">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="71b34-103">CorLaunchApplication Function</span></span>

<span data-ttu-id="71b34-104">Inicia la aplicación en la ruta de acceso de red especificada, usando los manifiestos especificados y otros datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71b34-104">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="71b34-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="71b34-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b34-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71b34-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="71b34-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71b34-107">Parameters</span></span>  

 `dwClickOnceHost`  
 <span data-ttu-id="71b34-108">de Un valor de la enumeración [HOST_TYPE](host-type-enumeration.md) que especifica el tipo de host que está iniciando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71b34-108">[in] A value of the [HOST_TYPE](host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="71b34-109">de Nombre completo de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="71b34-109">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="71b34-110">de El número de rutas de acceso de manifiesto para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71b34-110">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="71b34-111">de Matriz de cadenas, cada una de las cuales especifica una ruta de acceso a un manifiesto de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="71b34-111">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="71b34-112">de El número de elementos de datos de activación para la aplicación que se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="71b34-112">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="71b34-113">de Matriz de cadenas, cada una de las cuales es un elemento de datos de activación para la aplicación que se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="71b34-113">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="71b34-114">enuncia Puntero a información sobre el proceso en el que se ha cargado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="71b34-114">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71b34-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71b34-115">Requirements</span></span>  

 <span data-ttu-id="71b34-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71b34-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b34-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71b34-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71b34-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71b34-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71b34-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b34-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b34-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="71b34-120">See also</span></span>

- [<span data-ttu-id="71b34-121">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="71b34-121">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
