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
ms.openlocfilehash: bbf3c00eafe47556c6b46e1acb687a19df5a2b28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601767"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="15398-102">ICLRMetaHost::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="15398-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="15398-103">Intenta cerrar todos los runtime cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="15398-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="15398-104">Reemplaza el [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="15398-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15398-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15398-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15398-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15398-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="15398-107">[in] El código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="15398-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15398-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15398-108">Return Value</span></span>  
 <span data-ttu-id="15398-109">Este método nunca devuelve, por lo que su valor devuelto es indefinido.</span><span class="sxs-lookup"><span data-stu-id="15398-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15398-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15398-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15398-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15398-111">Requirements</span></span>  
 <span data-ttu-id="15398-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15398-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15398-113">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="15398-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15398-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15398-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15398-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15398-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15398-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="15398-116">See also</span></span>
- [<span data-ttu-id="15398-117">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15398-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="15398-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="15398-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
