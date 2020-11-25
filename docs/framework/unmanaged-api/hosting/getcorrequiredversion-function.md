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
ms.openlocfilehash: 9590d19f4e5f5890af53a108492bd1b6d130fb72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704505"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="f4246-102">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="f4246-102">GetCORRequiredVersion Function</span></span>

<span data-ttu-id="f4246-103">Obtiene el número de versión de Common Language Runtime (CLR) necesario.</span><span class="sxs-lookup"><span data-stu-id="f4246-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="f4246-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f4246-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4246-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4246-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4246-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4246-106">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="f4246-107">enuncia Un búfer que contiene una cadena que especifica el número de versión.</span><span class="sxs-lookup"><span data-stu-id="f4246-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f4246-108">de Tamaño, en bytes, del búfer.</span><span class="sxs-lookup"><span data-stu-id="f4246-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f4246-109">enuncia Número de bytes devueltos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="f4246-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4246-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4246-110">Requirements</span></span>  

 <span data-ttu-id="f4246-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4246-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4246-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4246-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4246-113">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4246-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4246-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4246-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4246-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4246-115">See also</span></span>

- [<span data-ttu-id="f4246-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f4246-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
