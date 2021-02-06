---
description: 'Más información acerca de: ICLRRuntimeInfo:: GetRuntimeDirectory ((método)'
title: ICLRRuntimeInfo::GetRuntimeDirectory (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: 1e833887568d0a61e9ff9ec358b6979a4bacce41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637097"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="6d76a-103">ICLRRuntimeInfo::GetRuntimeDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="6d76a-103">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="6d76a-104">Obtiene el directorio de instalación del Common Language Runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="6d76a-104">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="6d76a-105">Este método reemplaza la función [GetCORSystemDirectory (](getcorsystemdirectory-function.md) proporcionada en las versiones 2,0, 3,0 y 3,5 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d76a-105">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d76a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d76a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d76a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d76a-107">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="6d76a-108">enuncia Devuelve el directorio de instalación de CLR.</span><span class="sxs-lookup"><span data-stu-id="6d76a-108">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="6d76a-109">La ruta de instalación es completa; por ejemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705 \\ ".</span><span class="sxs-lookup"><span data-stu-id="6d76a-109">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="6d76a-110">[in, out] Especifica el tamaño de `pwzBuffer` para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="6d76a-110">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="6d76a-111">Si `pwzBuffer` es null, `pchBuffer` devuelve el tamaño requerido de `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="6d76a-111">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d76a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d76a-112">Return Value</span></span>  

 <span data-ttu-id="6d76a-113">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="6d76a-113">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6d76a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d76a-114">HRESULT</span></span>|<span data-ttu-id="6d76a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d76a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d76a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d76a-116">S_OK</span></span>|<span data-ttu-id="6d76a-117">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d76a-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="6d76a-118">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6d76a-118">E_POINTER</span></span>|<span data-ttu-id="6d76a-119">`pwzBuffer` o `pchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="6d76a-119">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d76a-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6d76a-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d76a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d76a-121">Requirements</span></span>  

 <span data-ttu-id="6d76a-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d76a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d76a-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="6d76a-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6d76a-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d76a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d76a-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d76a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d76a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d76a-126">See also</span></span>

- [<span data-ttu-id="6d76a-127">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d76a-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="6d76a-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="6d76a-128">Hosting</span></span>](index.md)
