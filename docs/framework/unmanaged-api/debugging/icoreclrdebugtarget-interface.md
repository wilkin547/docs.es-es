---
title: ICoreClrDebugTarget (interfaz)
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
ms.openlocfilehash: 190671b4f690f8c2cad43cf446a1196985ec5a42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790751"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="68b77-102">ICoreClrDebugTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68b77-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="68b77-103">Proporciona métodos que controlan los recuentos de referencias, enumeran los procesos y liberan la memoria asociada a un depurador que está asociado a un destino de Silverlight de Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="68b77-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68b77-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="68b77-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="68b77-105">Methods</span></span>  
  
|<span data-ttu-id="68b77-106">Método</span><span class="sxs-lookup"><span data-stu-id="68b77-106">Method</span></span>|<span data-ttu-id="68b77-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="68b77-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68b77-108">ICoreClrDebugTarget::EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="68b77-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="68b77-109">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="68b77-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="68b77-110">ICoreClrDebugTarget::EnumRuntimes (método)</span><span class="sxs-lookup"><span data-stu-id="68b77-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="68b77-111">Enumera Common Language Runtime (CLR) en el proceso especificado de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="68b77-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="68b77-112">ICoreClrDebugTarget::FreeMemory (método)</span><span class="sxs-lookup"><span data-stu-id="68b77-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="68b77-113">Libera la memoria asignada por los métodos de enumeración de esta clase.</span><span class="sxs-lookup"><span data-stu-id="68b77-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68b77-114">Notas</span><span class="sxs-lookup"><span data-stu-id="68b77-114">Remarks</span></span>  
 <span data-ttu-id="68b77-115">Actualmente, esta funcionalidad solo se admite para depurar un destino de aplicación basado en Silverlight que se ejecute en un equipo remoto de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="68b77-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b77-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="68b77-116">Requirements</span></span>  
 <span data-ttu-id="68b77-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68b77-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68b77-118">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="68b77-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="68b77-119">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="68b77-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="68b77-120">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="68b77-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b77-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="68b77-121">See also</span></span>

- [<span data-ttu-id="68b77-122">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68b77-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="68b77-123">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68b77-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="68b77-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="68b77-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
