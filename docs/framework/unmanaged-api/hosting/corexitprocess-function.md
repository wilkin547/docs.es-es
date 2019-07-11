---
title: CorExitProcess (Función)
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7aaa0e83de1b1c3e2ce436de04a36addef16c057
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758519"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="ca147-102">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="ca147-102">CorExitProcess Function</span></span>
<span data-ttu-id="ca147-103">Se cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="ca147-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="ca147-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ca147-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="ca147-105">Use la [ICLRMetaHost:: ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ca147-105">Use the [ICLRMetaHost::ExitProcess](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca147-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca147-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (   
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca147-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca147-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="ca147-108">Un entero que especifica el código de salida.</span><span class="sxs-lookup"><span data-stu-id="ca147-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca147-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca147-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca147-110">A partir de .NET Framework 4, `CorExitProcess` se cierra cada runtime iniciado en el proceso, no solo el tiempo de ejecución a la que se han enlazado las API heredadas.</span><span class="sxs-lookup"><span data-stu-id="ca147-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca147-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca147-111">Requirements</span></span>  
 <span data-ttu-id="ca147-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca147-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca147-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca147-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca147-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca147-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca147-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca147-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca147-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca147-116">See also</span></span>

- [<span data-ttu-id="ca147-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ca147-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
