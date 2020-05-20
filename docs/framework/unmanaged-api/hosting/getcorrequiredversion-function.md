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
ms.openlocfilehash: 6b9fd62102056a8d5f859ac913f4786f04c1df7e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617248"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="9906b-102">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="9906b-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="9906b-103">Obtiene el número de versión de Common Language Runtime (CLR) necesario.</span><span class="sxs-lookup"><span data-stu-id="9906b-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="9906b-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9906b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9906b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9906b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9906b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9906b-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="9906b-107">enuncia Un búfer que contiene una cadena que especifica el número de versión.</span><span class="sxs-lookup"><span data-stu-id="9906b-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9906b-108">de Tamaño, en bytes, del búfer.</span><span class="sxs-lookup"><span data-stu-id="9906b-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9906b-109">enuncia Número de bytes devueltos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="9906b-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9906b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9906b-110">Requirements</span></span>  
 <span data-ttu-id="9906b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9906b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9906b-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9906b-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9906b-113">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9906b-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9906b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9906b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9906b-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9906b-115">See also</span></span>

- [<span data-ttu-id="9906b-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9906b-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
