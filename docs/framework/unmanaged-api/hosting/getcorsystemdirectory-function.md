---
title: "GetCORSystemDirectory (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORSystemDirectory
helpviewer_keywords: GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02b695ac7f75dd38da8cd06e1444af4ae425ebd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="f4c61-102">GetCORSystemDirectory (Función)</span><span class="sxs-lookup"><span data-stu-id="f4c61-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="f4c61-103">Devuelve el directorio de instalación de common language runtime (CLR) que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f4c61-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="f4c61-104">El directorio de instalación está completo, por ejemplo, "c:\windows\microsoft.net\framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="f4c61-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="f4c61-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="f4c61-105">This function is deprecated.</span></span> <span data-ttu-id="f4c61-106">Sustituida por la [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) método proporcionado en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4c61-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c61-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4c61-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4c61-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4c61-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="f4c61-109">[out] Un búfer en el que el tiempo de ejecución devuelve una cadena que contiene el nombre completo del directorio de instalación para el tiempo de ejecución que se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f4c61-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="f4c61-110">Si el tiempo de ejecución aún no se han cargado en el proceso, la función devuelve la información de directorio adecuado para la versión más reciente del runtime instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f4c61-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f4c61-111">[in] El tamaño, en bytes, de `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="f4c61-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f4c61-112">[out] El número de caracteres devuelto en `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="f4c61-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4c61-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4c61-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f4c61-114">No use esta función en procesos que se ejecutan la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="f4c61-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="f4c61-115">Si está instalada una versión anterior de CLR en el equipo, esta función devuelve el directorio de instalación de esa versión.</span><span class="sxs-lookup"><span data-stu-id="f4c61-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c61-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4c61-116">Requirements</span></span>  
 <span data-ttu-id="f4c61-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4c61-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c61-118">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4c61-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4c61-119">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4c61-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4c61-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c61-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c61-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4c61-121">See Also</span></span>  
 [<span data-ttu-id="f4c61-122">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f4c61-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
