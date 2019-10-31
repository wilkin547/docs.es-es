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
ms.openlocfilehash: f197c8802bd9e55391b3e3e20c64398736070a16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136337"
---
# <a name="getfileversion-function"></a><span data-ttu-id="05012-102">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="05012-102">GetFileVersion Function</span></span>
<span data-ttu-id="05012-103">Obtiene la información de la versión de Common Language Runtime (CLR) del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="05012-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="05012-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="05012-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05012-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05012-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05012-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05012-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="05012-107">de Ruta de acceso del archivo que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="05012-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="05012-108">[in, out] Búfer asignado para la información de versión que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="05012-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="05012-109">de Tamaño, en caracteres anchos, de `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="05012-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="05012-110">enuncia Tamaño, en bytes, del `szBuffer`devuelto.</span><span class="sxs-lookup"><span data-stu-id="05012-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05012-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05012-111">Requirements</span></span>  
 <span data-ttu-id="05012-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05012-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05012-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="05012-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05012-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05012-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05012-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="05012-115">See also</span></span>

- [<span data-ttu-id="05012-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="05012-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
