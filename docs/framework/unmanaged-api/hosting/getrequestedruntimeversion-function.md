---
title: "GetRequestedRuntimeVersion (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersion
helpviewer_keywords: GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfac4e32841b8a8332a1f4124c1326f1ef7da1f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="3cb13-102">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="3cb13-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="3cb13-103">Obtiene el número de versión de common language runtime (CLR) solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="3cb13-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="3cb13-104">Si no está instalada esa versión, obtiene la versión más reciente que esté instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="3cb13-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="3cb13-105">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb13-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb13-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cb13-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cb13-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cb13-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="3cb13-108">[in] El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cb13-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="3cb13-109">[out] Un búfer que contiene la cadena del número de versión en la realización correcta.</span><span class="sxs-lookup"><span data-stu-id="3cb13-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="3cb13-110">[in] La longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="3cb13-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="3cb13-111">[out] Un puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="3cb13-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cb13-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3cb13-112">Return Value</span></span>  
 <span data-ttu-id="3cb13-113">Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="3cb13-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="3cb13-114">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="3cb13-114">Return code</span></span>|<span data-ttu-id="3cb13-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cb13-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3cb13-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cb13-116">S_OK</span></span>|<span data-ttu-id="3cb13-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3cb13-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="3cb13-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3cb13-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3cb13-119">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="3cb13-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="3cb13-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3cb13-120">E_POINTER</span></span>|<span data-ttu-id="3cb13-121">`pdwLength` es null.</span><span class="sxs-lookup"><span data-stu-id="3cb13-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cb13-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cb13-122">Requirements</span></span>  
 <span data-ttu-id="3cb13-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cb13-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cb13-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3cb13-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cb13-125">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cb13-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cb13-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cb13-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb13-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cb13-127">See Also</span></span>  
 [<span data-ttu-id="3cb13-128">GetRequestedRuntimeInfo (función)</span><span class="sxs-lookup"><span data-stu-id="3cb13-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="3cb13-129">GetVersionFromProcess (función)</span><span class="sxs-lookup"><span data-stu-id="3cb13-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [<span data-ttu-id="3cb13-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3cb13-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
