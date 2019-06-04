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
ms.openlocfilehash: bf63b2641c4140b287a3932c2073b445211ad3aa
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490370"
---
# <a name="getfileversion-function"></a><span data-ttu-id="9f970-102">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="9f970-102">GetFileVersion Function</span></span>
<span data-ttu-id="9f970-103">Obtiene la información de versión de common language runtime (CLR) del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="9f970-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="9f970-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9f970-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f970-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f970-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f970-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f970-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="9f970-107">[in] La ruta de acceso del archivo se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="9f970-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="9f970-108">[in, out] El búfer asignado para la información de versión que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="9f970-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9f970-109">[in] El tamaño, en caracteres anchos, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9f970-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9f970-110">[out] El tamaño, en bytes, del devuelto `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9f970-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f970-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f970-111">Requirements</span></span>  
 <span data-ttu-id="9f970-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f970-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f970-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f970-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f970-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f970-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f970-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f970-115">See also</span></span>

- [<span data-ttu-id="9f970-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9f970-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
