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
ms.openlocfilehash: b7a38d28b55842e9358bd9c7019b84c529526613
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617170"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="9f0b9-102">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="9f0b9-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="9f0b9-103">Obtiene el número de versión del Common Language Runtime (CLR) solicitado por la aplicación especificada.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="9f0b9-104">Si esa versión no está instalada, obtiene la versión más reciente instalada antes de la versión solicitada.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="9f0b9-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f0b9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f0b9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f0b9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f0b9-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="9f0b9-108">de El nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="9f0b9-109">enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9f0b9-110">de Longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="9f0b9-111">enuncia Puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f0b9-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f0b9-112">Return Value</span></span>  
 <span data-ttu-id="9f0b9-113">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="9f0b9-114">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="9f0b9-114">Return code</span></span>|<span data-ttu-id="9f0b9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f0b9-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9f0b9-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f0b9-116">S_OK</span></span>|<span data-ttu-id="9f0b9-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="9f0b9-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9f0b9-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9f0b9-119">El búfer de versión no es lo suficientemente grande como para almacenar la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="9f0b9-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9f0b9-120">E_POINTER</span></span>|<span data-ttu-id="9f0b9-121">`pdwLength` es null.</span><span class="sxs-lookup"><span data-stu-id="9f0b9-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f0b9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f0b9-122">Requirements</span></span>  
 <span data-ttu-id="9f0b9-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f0b9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f0b9-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9f0b9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f0b9-125">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f0b9-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f0b9-126">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f0b9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0b9-127">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9f0b9-127">See also</span></span>

- [<span data-ttu-id="9f0b9-128">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="9f0b9-128">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="9f0b9-129">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="9f0b9-129">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="9f0b9-130">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9f0b9-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
