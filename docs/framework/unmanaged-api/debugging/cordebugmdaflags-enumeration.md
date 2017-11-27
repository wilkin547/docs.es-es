---
title: "CorDebugMDAFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMDAFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMDAFlags
helpviewer_keywords: CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 827825e4012b421caa4e05702a6f1a1b863ac69d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="1c6a7-102">CorDebugMDAFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1c6a7-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="1c6a7-103">Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="1c6a7-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c6a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c6a7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1c6a7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1c6a7-105">Members</span></span>  
  
|<span data-ttu-id="1c6a7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1c6a7-106">Member</span></span>|<span data-ttu-id="1c6a7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c6a7-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="1c6a7-108">El subproceso en el que se activa el MDA ha cambiado desde que se inició el MDA.</span><span class="sxs-lookup"><span data-stu-id="1c6a7-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c6a7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c6a7-109">Remarks</span></span>  
 <span data-ttu-id="1c6a7-110">Cuando la pila de llamadas ya no describe dónde se generó originalmente el MDA, el subproceso se considera que tiene *pospuesto*.</span><span class="sxs-lookup"><span data-stu-id="1c6a7-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="1c6a7-111">Se trata de una circunstancia inusual producida por la ejecución del subproceso de una operación no válida al salir.</span><span class="sxs-lookup"><span data-stu-id="1c6a7-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c6a7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c6a7-112">Requirements</span></span>  
 <span data-ttu-id="1c6a7-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c6a7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c6a7-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c6a7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c6a7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c6a7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c6a7-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c6a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6a7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c6a7-117">See Also</span></span>  
 [<span data-ttu-id="1c6a7-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="1c6a7-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
