---
title: "GetCORRequiredVersion (Función)"
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
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65505243d7d1691f0458d614fd878b054916f113
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="38776-102">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="38776-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="38776-103">Obtiene el número de versión necesaria de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="38776-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="38776-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38776-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38776-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38776-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38776-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38776-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="38776-107">[out] Un búfer que contiene una cadena que especifica el número de versión.</span><span class="sxs-lookup"><span data-stu-id="38776-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="38776-108">[in] El tamaño, en bytes, del búfer.</span><span class="sxs-lookup"><span data-stu-id="38776-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="38776-109">[out] El número de bytes devueltos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="38776-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38776-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38776-110">Requirements</span></span>  
 <span data-ttu-id="38776-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38776-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38776-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38776-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38776-113">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38776-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38776-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38776-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38776-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="38776-115">See Also</span></span>  
 [<span data-ttu-id="38776-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="38776-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
