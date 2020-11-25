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
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730469"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="e5c32-102">ICLRMetaHost::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="e5c32-102">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="e5c32-103">Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="e5c32-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="e5c32-104">Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e5c32-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c32-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5c32-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5c32-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5c32-106">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="e5c32-107">de Código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="e5c32-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5c32-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5c32-108">Return Value</span></span>  

 <span data-ttu-id="e5c32-109">Este método nunca devuelve, por lo que el valor devuelto es indefinido.</span><span class="sxs-lookup"><span data-stu-id="e5c32-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5c32-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5c32-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c32-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5c32-111">Requirements</span></span>  

 <span data-ttu-id="e5c32-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5c32-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c32-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="e5c32-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e5c32-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5c32-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5c32-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c32-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c32-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5c32-116">See also</span></span>

- [<span data-ttu-id="e5c32-117">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5c32-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="e5c32-118">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e5c32-118">Hosting</span></span>](index.md)
