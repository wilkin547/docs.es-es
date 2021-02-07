---
description: 'Más información acerca de: ICLRMetaHost:: ExitProcess (método)'
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
ms.openlocfilehash: 3bc832538a5ad2b457de758fc35a632b09c02974
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689162"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="62a60-103">ICLRMetaHost::ExitProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="62a60-103">ICLRMetaHost::ExitProcess Method</span></span>

<span data-ttu-id="62a60-104">Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="62a60-104">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="62a60-105">Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="62a60-105">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a60-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62a60-106">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62a60-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62a60-107">Parameters</span></span>  

 `iExitCode`  
 <span data-ttu-id="62a60-108">de Código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="62a60-108">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62a60-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62a60-109">Return Value</span></span>  

 <span data-ttu-id="62a60-110">Este método nunca devuelve, por lo que el valor devuelto es indefinido.</span><span class="sxs-lookup"><span data-stu-id="62a60-110">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62a60-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62a60-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62a60-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62a60-112">Requirements</span></span>  

 <span data-ttu-id="62a60-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62a60-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62a60-114">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="62a60-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="62a60-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62a60-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62a60-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62a60-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a60-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="62a60-117">See also</span></span>

- [<span data-ttu-id="62a60-118">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62a60-118">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="62a60-119">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="62a60-119">Hosting</span></span>](index.md)
