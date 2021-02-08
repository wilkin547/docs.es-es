---
description: 'Más información acerca de: GetRequestedRuntimeVersion ((función)'
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
ms.openlocfilehash: 836cc4b875ddc427c6779950f5b68d2df8b6ef75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785281"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="59e75-103">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="59e75-103">GetRequestedRuntimeVersion Function</span></span>

<span data-ttu-id="59e75-104">Obtiene el número de versión del Common Language Runtime (CLR) solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="59e75-104">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="59e75-105">Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="59e75-105">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="59e75-106">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="59e75-106">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e75-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59e75-107">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e75-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59e75-108">Parameters</span></span>  

 `pExe`  
 <span data-ttu-id="59e75-109">de El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59e75-109">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="59e75-110">enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="59e75-110">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="59e75-111">de Longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="59e75-111">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="59e75-112">enuncia Puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="59e75-112">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59e75-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59e75-113">Return Value</span></span>  

 <span data-ttu-id="59e75-114">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="59e75-114">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="59e75-115">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="59e75-115">Return code</span></span>|<span data-ttu-id="59e75-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="59e75-116">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="59e75-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="59e75-117">S_OK</span></span>|<span data-ttu-id="59e75-118">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="59e75-118">The method completed successfully.</span></span>|  
|<span data-ttu-id="59e75-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="59e75-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="59e75-120">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="59e75-120">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="59e75-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="59e75-121">E_POINTER</span></span>|<span data-ttu-id="59e75-122">`pdwLength` es null.</span><span class="sxs-lookup"><span data-stu-id="59e75-122">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59e75-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59e75-123">Requirements</span></span>  

 <span data-ttu-id="59e75-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59e75-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e75-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="59e75-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59e75-126">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59e75-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59e75-127">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e75-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e75-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="59e75-128">See also</span></span>

- [<span data-ttu-id="59e75-129">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="59e75-129">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="59e75-130">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="59e75-130">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="59e75-131">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="59e75-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
