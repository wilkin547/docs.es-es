---
description: 'Más información acerca de: GetFileVersion ((función)'
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
ms.openlocfilehash: 7de19484f2f8123d61eb94e6a5ae09f56a3b5541
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785307"
---
# <a name="getfileversion-function"></a><span data-ttu-id="196cc-103">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="196cc-103">GetFileVersion Function</span></span>

<span data-ttu-id="196cc-104">Obtiene la información de la versión de Common Language Runtime (CLR) del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="196cc-104">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="196cc-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="196cc-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="196cc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="196cc-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="196cc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="196cc-107">Parameters</span></span>  

 `szFilename`  
 <span data-ttu-id="196cc-108">de Ruta de acceso del archivo que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="196cc-108">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="196cc-109">[in, out] Búfer asignado para la información de versión que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="196cc-109">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="196cc-110">de Tamaño, en caracteres anchos, de `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="196cc-110">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="196cc-111">enuncia Tamaño, en bytes, del devuelto `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="196cc-111">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="196cc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="196cc-112">Requirements</span></span>  

 <span data-ttu-id="196cc-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="196cc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="196cc-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="196cc-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="196cc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="196cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="196cc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="196cc-116">See also</span></span>

- [<span data-ttu-id="196cc-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="196cc-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
