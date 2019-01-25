---
title: GetCORRequiredVersion (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92ee0570a1a9bcc48cea744d5cc707750742d51a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534087"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="9920e-102">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="9920e-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="9920e-103">Obtiene el número de versión necesaria de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9920e-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="9920e-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9920e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9920e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9920e-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9920e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9920e-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="9920e-107">[out] Un búfer que contiene una cadena que especifica el número de versión.</span><span class="sxs-lookup"><span data-stu-id="9920e-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9920e-108">[in] El tamaño, en bytes, del búfer.</span><span class="sxs-lookup"><span data-stu-id="9920e-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9920e-109">[out] Devuelve el número de bytes en el búfer.</span><span class="sxs-lookup"><span data-stu-id="9920e-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9920e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9920e-110">Requirements</span></span>  
 <span data-ttu-id="9920e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9920e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9920e-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9920e-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9920e-113">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9920e-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9920e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9920e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9920e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9920e-115">See also</span></span>
- [<span data-ttu-id="9920e-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9920e-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
