---
description: 'Más información acerca de: CorExitProcess ((función)'
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
ms.openlocfilehash: 68d33dec76387e103a34e99c529a4e7aff7535b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649590"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="f02f5-103">CorExitProcess (Función)</span><span class="sxs-lookup"><span data-stu-id="f02f5-103">CorExitProcess Function</span></span>

<span data-ttu-id="f02f5-104">Cierra el proceso no administrado actual.</span><span class="sxs-lookup"><span data-stu-id="f02f5-104">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="f02f5-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f02f5-105">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="f02f5-106">Use en su lugar el método [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f02f5-106">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f02f5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f02f5-107">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f02f5-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f02f5-108">Parameters</span></span>  

 `exitCode`  
 <span data-ttu-id="f02f5-109">Un entero que especifica el código de salida del proceso.</span><span class="sxs-lookup"><span data-stu-id="f02f5-109">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f02f5-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f02f5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f02f5-111">A partir de la .NET Framework 4, `CorExitProcess` sale de cada tiempo de ejecución iniciado en el proceso, no solo el Runtime al que se han enlazado las API heredadas.</span><span class="sxs-lookup"><span data-stu-id="f02f5-111">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f02f5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f02f5-112">Requirements</span></span>  

 <span data-ttu-id="f02f5-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f02f5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f02f5-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f02f5-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f02f5-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f02f5-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f02f5-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f02f5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02f5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f02f5-117">See also</span></span>

- [<span data-ttu-id="f02f5-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="f02f5-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
