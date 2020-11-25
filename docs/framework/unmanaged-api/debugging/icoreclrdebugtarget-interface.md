---
title: ICoreClrDebugTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
ms.openlocfilehash: 791bd2754a96b97a38e2509c0c61a644324857cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716959"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="fc731-102">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc731-102">ICoreClrDebugTarget Interface</span></span>

<span data-ttu-id="fc731-103">Proporciona métodos que controlan los recuentos de referencias, enumeran los procesos y liberan la memoria asociada a un depurador que está asociado a un destino de Silverlight de Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="fc731-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc731-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc731-104">Syntax</span></span>  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fc731-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fc731-105">Methods</span></span>  
  
|<span data-ttu-id="fc731-106">Método</span><span class="sxs-lookup"><span data-stu-id="fc731-106">Method</span></span>|<span data-ttu-id="fc731-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc731-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc731-108">ICoreClrDebugTarget::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="fc731-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="fc731-109">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="fc731-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="fc731-110">ICoreClrDebugTarget::EnumRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="fc731-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="fc731-111">Enumera Common Language Runtime (CLR) en el proceso especificado de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="fc731-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="fc731-112">ICoreClrDebugTarget::FreeMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="fc731-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="fc731-113">Libera la memoria asignada por los métodos de enumeración de esta clase.</span><span class="sxs-lookup"><span data-stu-id="fc731-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc731-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc731-114">Remarks</span></span>  

 <span data-ttu-id="fc731-115">Actualmente, esta funcionalidad solo se admite para depurar un destino de aplicación basado en Silverlight que se ejecute en un equipo remoto de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="fc731-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc731-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc731-116">Requirements</span></span>  

 <span data-ttu-id="fc731-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc731-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc731-118">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="fc731-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="fc731-119">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="fc731-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="fc731-120">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="fc731-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc731-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc731-121">See also</span></span>

- [<span data-ttu-id="fc731-122">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc731-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="fc731-123">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc731-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="fc731-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fc731-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
