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
ms.openlocfilehash: f6d8114732a3b7c15d0a0258a28a362d661b030a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673649"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="15844-102">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="15844-102">CorExitProcess Function</span></span>

<span data-ttu-id="15844-103">Cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="15844-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="15844-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="15844-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="15844-105">Use en su lugar el método [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="15844-105">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15844-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15844-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15844-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15844-107">Parameters</span></span>  

 `exitCode`  
 <span data-ttu-id="15844-108">Un entero que especifica el código de salida del proceso.</span><span class="sxs-lookup"><span data-stu-id="15844-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15844-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15844-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15844-110">A partir de la .NET Framework 4, `CorExitProcess` sale de cada tiempo de ejecución iniciado en el proceso, no solo el Runtime al que se han enlazado las API heredadas.</span><span class="sxs-lookup"><span data-stu-id="15844-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15844-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15844-111">Requirements</span></span>  

 <span data-ttu-id="15844-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15844-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15844-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="15844-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15844-114">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15844-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15844-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15844-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15844-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15844-116">See also</span></span>

- [<span data-ttu-id="15844-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="15844-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
