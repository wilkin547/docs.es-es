---
title: GetFileVersion (Función)
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b772de720a8c3b669bd3cbe9591637d931cb8763
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430624"
---
# <a name="getfileversion-function"></a><span data-ttu-id="bb930-102">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="bb930-102">GetFileVersion Function</span></span>
<span data-ttu-id="bb930-103">Obtiene la información de versión de common language runtime (CLR) del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="bb930-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="bb930-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb930-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb930-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb930-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb930-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb930-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="bb930-107">[in] La ruta de acceso del archivo que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="bb930-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="bb930-108">[entrada, salida] El búfer asignado para la información de versión que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="bb930-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="bb930-109">[in] El tamaño, en caracteres anchos, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="bb930-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="bb930-110">[out] El tamaño, en bytes, del devuelto `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="bb930-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb930-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb930-111">Requirements</span></span>  
 <span data-ttu-id="bb930-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb930-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb930-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bb930-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb930-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb930-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb930-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb930-115">See Also</span></span>  
 [<span data-ttu-id="bb930-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="bb930-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
