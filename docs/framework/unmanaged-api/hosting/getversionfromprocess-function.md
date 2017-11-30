---
title: "GetVersionFromProcess (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetVersionFromProcess
helpviewer_keywords: GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c73d12731a5c72b8c0e724f74ee0aa9ebddeee9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="e9c98-102">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="e9c98-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="e9c98-103">Obtiene el número de versión de common language runtime (CLR) que está asociado con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="e9c98-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="e9c98-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9c98-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c98-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9c98-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9c98-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9c98-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="e9c98-107">[in] Un identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="e9c98-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="e9c98-108">[out] Un búfer que contiene la cadena del número de versión en la realización correcta del método.</span><span class="sxs-lookup"><span data-stu-id="e9c98-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e9c98-109">[in] La longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="e9c98-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="e9c98-110">[out] Un puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="e9c98-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9c98-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9c98-111">Return Value</span></span>  
 <span data-ttu-id="e9c98-112">Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="e9c98-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="e9c98-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="e9c98-113">Return code</span></span>|<span data-ttu-id="e9c98-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9c98-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e9c98-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9c98-115">S_OK</span></span>|<span data-ttu-id="e9c98-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9c98-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="e9c98-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e9c98-117">E_INVALIDARG</span></span>|<span data-ttu-id="e9c98-118">`pVersion`es null y `cchBuffer` no es null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e9c98-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="e9c98-119">O bien</span><span class="sxs-lookup"><span data-stu-id="e9c98-119">-or-</span></span><br /><br /> <span data-ttu-id="e9c98-120">`hProcess`no es un identificador válido para un proceso.</span><span class="sxs-lookup"><span data-stu-id="e9c98-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="e9c98-121">O bien</span><span class="sxs-lookup"><span data-stu-id="e9c98-121">-or-</span></span><br /><br /> <span data-ttu-id="e9c98-122">El CLR no está cargado.</span><span class="sxs-lookup"><span data-stu-id="e9c98-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="e9c98-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e9c98-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e9c98-124">`cchBuffer`es nulo o menor que la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="e9c98-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="e9c98-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e9c98-125">E_NOTIMPL</span></span>|<span data-ttu-id="e9c98-126">Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="e9c98-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9c98-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9c98-127">Requirements</span></span>  
 <span data-ttu-id="e9c98-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c98-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c98-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9c98-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9c98-130">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9c98-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9c98-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c98-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c98-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9c98-132">See Also</span></span>  
 [<span data-ttu-id="e9c98-133">GetRequestedRuntimeInfo (función)</span><span class="sxs-lookup"><span data-stu-id="e9c98-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="e9c98-134">GetRequestedRuntimeVersion (función)</span><span class="sxs-lookup"><span data-stu-id="e9c98-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="e9c98-135">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e9c98-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
