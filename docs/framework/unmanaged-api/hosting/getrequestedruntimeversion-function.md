---
title: GetRequestedRuntimeVersion (Función)
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: be7d6ce29a9c9c4e3e530df40432b1a4c3b2d389
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136342"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="a66b3-102">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="a66b3-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="a66b3-103">Obtiene el número de versión del Common Language Runtime (CLR) solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="a66b3-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="a66b3-104">Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="a66b3-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="a66b3-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a66b3-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a66b3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a66b3-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a66b3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a66b3-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="a66b3-108">de El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a66b3-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="a66b3-109">enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="a66b3-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a66b3-110">de Longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="a66b3-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="a66b3-111">enuncia Puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="a66b3-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a66b3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a66b3-112">Return Value</span></span>  
 <span data-ttu-id="a66b3-113">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="a66b3-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a66b3-114">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="a66b3-114">Return code</span></span>|<span data-ttu-id="a66b3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a66b3-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a66b3-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a66b3-116">S_OK</span></span>|<span data-ttu-id="a66b3-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a66b3-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="a66b3-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a66b3-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a66b3-119">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="a66b3-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="a66b3-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a66b3-120">E_POINTER</span></span>|<span data-ttu-id="a66b3-121">`pdwLength` es null.</span><span class="sxs-lookup"><span data-stu-id="a66b3-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a66b3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a66b3-122">Requirements</span></span>  
 <span data-ttu-id="a66b3-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a66b3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a66b3-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a66b3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a66b3-125">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a66b3-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a66b3-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a66b3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66b3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a66b3-127">See also</span></span>

- [<span data-ttu-id="a66b3-128">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="a66b3-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="a66b3-129">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="a66b3-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="a66b3-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="a66b3-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
