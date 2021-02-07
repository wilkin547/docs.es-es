---
description: 'Más información acerca de: interfaz ICoreClrDebugTarget'
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
ms.openlocfilehash: f0ed4dd75cd1daca6e83617433b29bbaecb1dd36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728761"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="198b5-103">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="198b5-103">ICoreClrDebugTarget Interface</span></span>

<span data-ttu-id="198b5-104">Proporciona métodos que controlan los recuentos de referencias, enumeran los procesos y liberan la memoria asociada a un depurador que está asociado a un destino de Silverlight de Macintosh remoto.</span><span class="sxs-lookup"><span data-stu-id="198b5-104">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="198b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="198b5-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="198b5-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="198b5-106">Methods</span></span>  
  
|<span data-ttu-id="198b5-107">Método</span><span class="sxs-lookup"><span data-stu-id="198b5-107">Method</span></span>|<span data-ttu-id="198b5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="198b5-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="198b5-109">ICoreClrDebugTarget::EnumProcesses (Método)</span><span class="sxs-lookup"><span data-stu-id="198b5-109">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="198b5-110">Enumera los procesos que se ejecutan en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="198b5-110">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="198b5-111">ICoreClrDebugTarget::EnumRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="198b5-111">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="198b5-112">Enumera Common Language Runtime (CLR) en el proceso especificado de un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="198b5-112">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="198b5-113">ICoreClrDebugTarget::FreeMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="198b5-113">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="198b5-114">Libera la memoria asignada por los métodos de enumeración de esta clase.</span><span class="sxs-lookup"><span data-stu-id="198b5-114">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="198b5-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="198b5-115">Remarks</span></span>  

 <span data-ttu-id="198b5-116">Actualmente, esta funcionalidad solo se admite para depurar un destino de aplicación basado en Silverlight que se ejecute en un equipo remoto de Macintosh.</span><span class="sxs-lookup"><span data-stu-id="198b5-116">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="198b5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="198b5-117">Requirements</span></span>  

 <span data-ttu-id="198b5-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="198b5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="198b5-119">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="198b5-119">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="198b5-120">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="198b5-120">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="198b5-121">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="198b5-121">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="198b5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="198b5-122">See also</span></span>

- [<span data-ttu-id="198b5-123">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="198b5-123">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="198b5-124">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="198b5-124">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="198b5-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="198b5-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
