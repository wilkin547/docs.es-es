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
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178137"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="fcfef-102">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="fcfef-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="fcfef-103">Obtiene el número de versión de Common Language Runtime (CLR) solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="fcfef-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="fcfef-104">Si esa versión no está instalada, obtiene la versión más reciente que se instala antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="fcfef-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="fcfef-105">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fcfef-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcfef-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcfef-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcfef-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcfef-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="fcfef-108">[en] El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fcfef-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="fcfef-109">[fuera] Un búfer que contiene la cadena de número de versión una vez completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="fcfef-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="fcfef-110">[en] La longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="fcfef-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="fcfef-111">[fuera] Un puntero a la longitud de la cadena de número de versión.</span><span class="sxs-lookup"><span data-stu-id="fcfef-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcfef-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fcfef-112">Return Value</span></span>  
 <span data-ttu-id="fcfef-113">Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="fcfef-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="fcfef-114">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="fcfef-114">Return code</span></span>|<span data-ttu-id="fcfef-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcfef-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fcfef-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcfef-116">S_OK</span></span>|<span data-ttu-id="fcfef-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fcfef-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="fcfef-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fcfef-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="fcfef-119">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="fcfef-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="fcfef-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fcfef-120">E_POINTER</span></span>|<span data-ttu-id="fcfef-121">`pdwLength` es null.</span><span class="sxs-lookup"><span data-stu-id="fcfef-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcfef-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcfef-122">Requirements</span></span>  
 <span data-ttu-id="fcfef-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcfef-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcfef-124">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="fcfef-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcfef-125">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fcfef-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcfef-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcfef-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcfef-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcfef-127">See also</span></span>

- [<span data-ttu-id="fcfef-128">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="fcfef-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="fcfef-129">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="fcfef-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="fcfef-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="fcfef-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
