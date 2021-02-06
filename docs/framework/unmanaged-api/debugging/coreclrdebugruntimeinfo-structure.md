---
description: 'Más información acerca de: estructura Coreclrdebugruntimeinfo ('
title: CoreClrDebugRuntimeInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
ms.openlocfilehash: 588e8bd1598996d1676e2df5517bd9a52eb59df4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661719"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="81c1b-103">CoreClrDebugRuntimeInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="81c1b-103">CoreClrDebugRuntimeInfo Structure</span></span>

<span data-ttu-id="81c1b-104">Representa una instancia de Common Language Runtime (CLR) que se carga en un proceso en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="81c1b-104">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81c1b-105">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="81c1b-106">Members</span><span class="sxs-lookup"><span data-stu-id="81c1b-106">Members</span></span>  
  
|<span data-ttu-id="81c1b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="81c1b-107">Member</span></span>|<span data-ttu-id="81c1b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="81c1b-108">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="81c1b-109">Identificador en tiempo de ejecución asignado por el proxy de depuración remota en ejecución en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="81c1b-109">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81c1b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81c1b-110">Requirements</span></span>  

 <span data-ttu-id="81c1b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81c1b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81c1b-112">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="81c1b-112">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="81c1b-113">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="81c1b-113">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="81c1b-114">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="81c1b-114">**.NET Framework Versions:** 3.5 SP1</span></span>
