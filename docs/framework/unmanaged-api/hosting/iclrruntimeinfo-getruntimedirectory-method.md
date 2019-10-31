---
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
ms.openlocfilehash: b0a2e5f259fe1ee566f9cc25152b2d2a1f740bea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120338"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="a0b11-102">ICLRRuntimeInfo::GetRuntimeDirectory (Método)</span><span class="sxs-lookup"><span data-stu-id="a0b11-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="a0b11-103">Obtiene el directorio de instalación del Common Language Runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="a0b11-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="a0b11-104">Este método reemplaza la función [GetCORSystemDirectory (](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) proporcionada en las versiones 2,0, 3,0 y 3,5 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0b11-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b11-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0b11-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b11-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0b11-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="a0b11-107">enuncia Devuelve el directorio de instalación de CLR.</span><span class="sxs-lookup"><span data-stu-id="a0b11-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="a0b11-108">La ruta de instalación es completa; por ejemplo, "c:\Windows\Microsoft.NET\Framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="a0b11-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="a0b11-109">[in, out] Especifica el tamaño de `pwzBuffer` para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="a0b11-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="a0b11-110">Si `pwzBuffer` es null, `pchBuffer` devuelve el tamaño necesario de `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="a0b11-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0b11-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0b11-111">Return Value</span></span>  
 <span data-ttu-id="a0b11-112">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a0b11-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a0b11-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0b11-113">HRESULT</span></span>|<span data-ttu-id="a0b11-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0b11-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0b11-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0b11-115">S_OK</span></span>|<span data-ttu-id="a0b11-116">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0b11-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="a0b11-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a0b11-117">E_POINTER</span></span>|<span data-ttu-id="a0b11-118">`pwzBuffer` o `pchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="a0b11-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0b11-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0b11-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b11-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0b11-120">Requirements</span></span>  
 <span data-ttu-id="a0b11-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0b11-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b11-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a0b11-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a0b11-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a0b11-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0b11-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b11-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b11-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0b11-125">See also</span></span>

- [<span data-ttu-id="a0b11-126">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0b11-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a0b11-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a0b11-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
