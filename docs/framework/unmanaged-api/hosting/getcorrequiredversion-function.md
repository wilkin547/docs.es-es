---
description: 'Más información acerca de: Getcorrequiredversion ((función)'
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
ms.openlocfilehash: ea1b928054e3ec6080b00e2a41228035f50c0f84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785359"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="b1472-103">GetCORRequiredVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="b1472-103">GetCORRequiredVersion Function</span></span>

<span data-ttu-id="b1472-104">Obtiene el número de versión de Common Language Runtime (CLR) necesario.</span><span class="sxs-lookup"><span data-stu-id="b1472-104">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="b1472-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b1472-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1472-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1472-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1472-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1472-107">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="b1472-108">enuncia Un búfer que contiene una cadena que especifica el número de versión.</span><span class="sxs-lookup"><span data-stu-id="b1472-108">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b1472-109">de Tamaño, en bytes, del búfer.</span><span class="sxs-lookup"><span data-stu-id="b1472-109">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b1472-110">enuncia Número de bytes devueltos en el búfer.</span><span class="sxs-lookup"><span data-stu-id="b1472-110">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1472-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1472-111">Requirements</span></span>  

 <span data-ttu-id="b1472-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1472-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1472-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b1472-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1472-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1472-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1472-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1472-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1472-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1472-116">See also</span></span>

- [<span data-ttu-id="b1472-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="b1472-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
