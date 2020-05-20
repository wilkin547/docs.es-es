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
ms.openlocfilehash: 2dd004a44b20d48dafc72711ac23abcb55739224
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617205"
---
# <a name="getfileversion-function"></a><span data-ttu-id="317c6-102">GetFileVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="317c6-102">GetFileVersion Function</span></span>
<span data-ttu-id="317c6-103">Obtiene la información de la versión de Common Language Runtime (CLR) del archivo especificado, utilizando el búfer especificado.</span><span class="sxs-lookup"><span data-stu-id="317c6-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="317c6-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="317c6-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="317c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="317c6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="317c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="317c6-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="317c6-107">de Ruta de acceso del archivo que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="317c6-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="317c6-108">[in, out] Búfer asignado para la información de versión que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="317c6-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="317c6-109">de Tamaño, en caracteres anchos, de `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="317c6-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="317c6-110">enuncia Tamaño, en bytes, del devuelto `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="317c6-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="317c6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="317c6-111">Requirements</span></span>  
 <span data-ttu-id="317c6-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="317c6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="317c6-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="317c6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="317c6-114">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="317c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="317c6-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="317c6-115">See also</span></span>

- [<span data-ttu-id="317c6-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="317c6-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
