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
ms.openlocfilehash: d8643c54950486b6374045ff83928c8c7fb568a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140954"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="d7600-102">ICLRMetaHost::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="d7600-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="d7600-103">Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="d7600-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="d7600-104">Reemplaza la función [CorExitProcess (](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d7600-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7600-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7600-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7600-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7600-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="d7600-107">de Código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="d7600-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7600-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d7600-108">Return Value</span></span>  
 <span data-ttu-id="d7600-109">Este método nunca devuelve, por lo que el valor devuelto es indefinido.</span><span class="sxs-lookup"><span data-stu-id="d7600-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7600-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7600-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7600-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7600-111">Requirements</span></span>  
 <span data-ttu-id="d7600-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7600-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7600-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d7600-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d7600-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7600-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7600-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7600-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7600-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7600-116">See also</span></span>

- [<span data-ttu-id="d7600-117">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7600-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="d7600-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d7600-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
