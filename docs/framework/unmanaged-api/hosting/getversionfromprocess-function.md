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
ms.openlocfilehash: da0d159da6eef7745c1fa7f7320d5e1355f6e413
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721886"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="fd052-102">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="fd052-102">GetVersionFromProcess Function</span></span>

<span data-ttu-id="fd052-103">Obtiene el número de versión del Common Language Runtime (CLR) que está asociado al identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="fd052-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="fd052-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fd052-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd052-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd052-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd052-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd052-106">Parameters</span></span>  

 `hProcess`  
 <span data-ttu-id="fd052-107">de Identificador de un proceso.</span><span class="sxs-lookup"><span data-stu-id="fd052-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="fd052-108">enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente el método.</span><span class="sxs-lookup"><span data-stu-id="fd052-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="fd052-109">de Longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="fd052-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="fd052-110">enuncia Puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="fd052-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd052-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd052-111">Return Value</span></span>  

 <span data-ttu-id="fd052-112">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="fd052-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="fd052-113">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="fd052-113">Return code</span></span>|<span data-ttu-id="fd052-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd052-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fd052-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd052-115">S_OK</span></span>|<span data-ttu-id="fd052-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd052-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="fd052-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fd052-117">E_INVALIDARG</span></span>|<span data-ttu-id="fd052-118">`pVersion` es NULL y `cchBuffer` no es null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="fd052-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="fd052-119">o bien</span><span class="sxs-lookup"><span data-stu-id="fd052-119">-or-</span></span><br /><br /> <span data-ttu-id="fd052-120">`hProcess` no es un identificador válido para un proceso.</span><span class="sxs-lookup"><span data-stu-id="fd052-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="fd052-121">o bien</span><span class="sxs-lookup"><span data-stu-id="fd052-121">-or-</span></span><br /><br /> <span data-ttu-id="fd052-122">CLR no está cargado.</span><span class="sxs-lookup"><span data-stu-id="fd052-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="fd052-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fd052-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="fd052-124">`cchBuffer` es null o menor que la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="fd052-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="fd052-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fd052-125">E_NOTIMPL</span></span>|<span data-ttu-id="fd052-126">Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="fd052-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd052-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd052-127">Requirements</span></span>  

 <span data-ttu-id="fd052-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd052-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd052-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd052-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd052-130">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd052-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd052-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd052-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd052-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd052-132">See also</span></span>

- [<span data-ttu-id="fd052-133">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="fd052-133">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="fd052-134">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="fd052-134">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="fd052-135">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="fd052-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
