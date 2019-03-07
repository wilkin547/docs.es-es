---
title: GetVersionFromProcess (Función)
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fad069a15cb4079dac2b4ee65ca3d9669a53cac0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479268"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="29b33-102">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="29b33-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="29b33-103">Obtiene el número de versión de common language runtime (CLR) que está asociado con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="29b33-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="29b33-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29b33-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29b33-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29b33-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29b33-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29b33-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="29b33-107">[in] Un identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="29b33-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="29b33-108">[out] Un búfer que contiene la cadena de número de versión tras la finalización correcta del método.</span><span class="sxs-lookup"><span data-stu-id="29b33-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="29b33-109">[in] La longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="29b33-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="29b33-110">[out] Un puntero a la longitud de la cadena de número de versión.</span><span class="sxs-lookup"><span data-stu-id="29b33-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29b33-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="29b33-111">Return Value</span></span>  
 <span data-ttu-id="29b33-112">Este método devuelve códigos de error de modelo de objetos componentes (COM) estándar, tal como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="29b33-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="29b33-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="29b33-113">Return code</span></span>|<span data-ttu-id="29b33-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="29b33-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="29b33-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="29b33-115">S_OK</span></span>|<span data-ttu-id="29b33-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="29b33-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="29b33-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="29b33-117">E_INVALIDARG</span></span>|<span data-ttu-id="29b33-118">`pVersion` es null y `cchBuffer` no es null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="29b33-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="29b33-119">O bien</span><span class="sxs-lookup"><span data-stu-id="29b33-119">-or-</span></span><br /><br /> <span data-ttu-id="29b33-120">`hProcess` no es un identificador válido para un proceso.</span><span class="sxs-lookup"><span data-stu-id="29b33-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="29b33-121">O bien</span><span class="sxs-lookup"><span data-stu-id="29b33-121">-or-</span></span><br /><br /> <span data-ttu-id="29b33-122">No se carga el CLR.</span><span class="sxs-lookup"><span data-stu-id="29b33-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="29b33-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="29b33-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="29b33-124">`cchBuffer` es nulo o menor que la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="29b33-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="29b33-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="29b33-125">E_NOTIMPL</span></span>|<span data-ttu-id="29b33-126">Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Windows Millennium Edition de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="29b33-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29b33-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29b33-127">Requirements</span></span>  
 <span data-ttu-id="29b33-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29b33-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29b33-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29b33-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29b33-130">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29b33-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29b33-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29b33-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b33-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="29b33-132">See also</span></span>
- [<span data-ttu-id="29b33-133">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="29b33-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="29b33-134">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="29b33-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="29b33-135">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="29b33-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
