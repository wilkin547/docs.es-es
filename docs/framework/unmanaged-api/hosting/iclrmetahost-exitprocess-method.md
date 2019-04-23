---
title: ICLRMetaHost::ExitProcess (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64c212d064ad658678926690d1e680afe27c7c99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219244"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="a2ed6-102">ICLRMetaHost::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="a2ed6-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="a2ed6-103">Intenta cerrar todos los runtime cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="a2ed6-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="a2ed6-104">Reemplaza el [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="a2ed6-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2ed6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2ed6-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2ed6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2ed6-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="a2ed6-107">[in] El código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="a2ed6-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2ed6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a2ed6-108">Return Value</span></span>  
 <span data-ttu-id="a2ed6-109">Este método nunca devuelve, por lo que su valor devuelto es indefinido.</span><span class="sxs-lookup"><span data-stu-id="a2ed6-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2ed6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2ed6-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2ed6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2ed6-111">Requirements</span></span>  
 <span data-ttu-id="a2ed6-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2ed6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2ed6-113">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a2ed6-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a2ed6-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2ed6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2ed6-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2ed6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ed6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2ed6-116">See also</span></span>

- [<span data-ttu-id="a2ed6-117">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2ed6-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="a2ed6-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a2ed6-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
