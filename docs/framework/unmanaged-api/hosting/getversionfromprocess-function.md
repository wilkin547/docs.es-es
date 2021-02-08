---
description: 'Más información acerca de: GetVersionFromProcess ((función)'
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
ms.openlocfilehash: ab665d2984f79baf049009690b36782528094937
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785255"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="c8cda-103">GetVersionFromProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="c8cda-103">GetVersionFromProcess Function</span></span>

<span data-ttu-id="c8cda-104">Obtiene el número de versión del Common Language Runtime (CLR) que está asociado al identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c8cda-104">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="c8cda-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c8cda-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cda-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8cda-106">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8cda-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8cda-107">Parameters</span></span>  

 `hProcess`  
 <span data-ttu-id="c8cda-108">de Identificador de un proceso.</span><span class="sxs-lookup"><span data-stu-id="c8cda-108">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="c8cda-109">enuncia Un búfer que contiene la cadena del número de versión cuando se completa correctamente el método.</span><span class="sxs-lookup"><span data-stu-id="c8cda-109">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c8cda-110">de Longitud del búfer de versión.</span><span class="sxs-lookup"><span data-stu-id="c8cda-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="c8cda-111">enuncia Puntero a la longitud de la cadena del número de versión.</span><span class="sxs-lookup"><span data-stu-id="c8cda-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8cda-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c8cda-112">Return Value</span></span>  

 <span data-ttu-id="c8cda-113">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="c8cda-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="c8cda-114">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="c8cda-114">Return code</span></span>|<span data-ttu-id="c8cda-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8cda-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c8cda-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8cda-116">S_OK</span></span>|<span data-ttu-id="c8cda-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c8cda-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="c8cda-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c8cda-118">E_INVALIDARG</span></span>|<span data-ttu-id="c8cda-119">`pVersion` es NULL y `cchBuffer` no es null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="c8cda-119">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="c8cda-120">o bien</span><span class="sxs-lookup"><span data-stu-id="c8cda-120">-or-</span></span><br /><br /> <span data-ttu-id="c8cda-121">`hProcess` no es un identificador válido para un proceso.</span><span class="sxs-lookup"><span data-stu-id="c8cda-121">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="c8cda-122">o bien</span><span class="sxs-lookup"><span data-stu-id="c8cda-122">-or-</span></span><br /><br /> <span data-ttu-id="c8cda-123">CLR no está cargado.</span><span class="sxs-lookup"><span data-stu-id="c8cda-123">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="c8cda-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c8cda-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c8cda-125">`cchBuffer` es null o menor que la longitud de la cadena de versión.</span><span class="sxs-lookup"><span data-stu-id="c8cda-125">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="c8cda-126">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c8cda-126">E_NOTIMPL</span></span>|<span data-ttu-id="c8cda-127">Este método no está disponible en el sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="c8cda-127">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8cda-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8cda-128">Requirements</span></span>  

 <span data-ttu-id="c8cda-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8cda-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8cda-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c8cda-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8cda-131">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8cda-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8cda-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8cda-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8cda-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8cda-133">See also</span></span>

- [<span data-ttu-id="c8cda-134">GetRequestedRuntimeInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c8cda-134">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="c8cda-135">GetRequestedRuntimeVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="c8cda-135">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="c8cda-136">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c8cda-136">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
