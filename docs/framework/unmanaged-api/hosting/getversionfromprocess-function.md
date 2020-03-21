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
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178129"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="a3ec7-102">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="a3ec7-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="a3ec7-103">Obtiene el número de versión de Common Language Runtime (CLR) asociado al identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="a3ec7-104">Esta función ha quedado en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ec7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3ec7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3ec7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3ec7-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="a3ec7-107">[en] Un identificador de un proceso.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="a3ec7-108">[fuera] Un búfer que contiene la cadena de número de versión al completar correctamente el método.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a3ec7-109">[en] La longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="a3ec7-110">[fuera] Un puntero a la longitud de la cadena de número de versión.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3ec7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3ec7-111">Return Value</span></span>  
 <span data-ttu-id="a3ec7-112">Este método devuelve códigos de error estándar del modelo de objetos componentes (COM), tal como se define en WinError.h, además de los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a3ec7-113">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="a3ec7-113">Return code</span></span>|<span data-ttu-id="a3ec7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3ec7-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a3ec7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3ec7-115">S_OK</span></span>|<span data-ttu-id="a3ec7-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="a3ec7-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a3ec7-117">E_INVALIDARG</span></span>|<span data-ttu-id="a3ec7-118">`pVersion`es null `cchBuffer` y no es null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="a3ec7-119">O bien</span><span class="sxs-lookup"><span data-stu-id="a3ec7-119">-or-</span></span><br /><br /> <span data-ttu-id="a3ec7-120">`hProcess`no es un identificador válido para un proceso.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="a3ec7-121">O bien</span><span class="sxs-lookup"><span data-stu-id="a3ec7-121">-or-</span></span><br /><br /> <span data-ttu-id="a3ec7-122">El CLR no se carga.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="a3ec7-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a3ec7-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a3ec7-124">`cchBuffer`es null o menor que la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="a3ec7-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a3ec7-125">E_NOTIMPL</span></span>|<span data-ttu-id="a3ec7-126">Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="a3ec7-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3ec7-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3ec7-127">Requirements</span></span>  
 <span data-ttu-id="a3ec7-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3ec7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3ec7-129">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3ec7-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3ec7-130">**Biblioteca:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a3ec7-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3ec7-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3ec7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ec7-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3ec7-132">See also</span></span>

- [<span data-ttu-id="a3ec7-133">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="a3ec7-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="a3ec7-134">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="a3ec7-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="a3ec7-135">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="a3ec7-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
