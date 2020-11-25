---
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
ms.openlocfilehash: 3cc9a1cfb26a784c32d66168bb01d41f91dd5f66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722393"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="874df-102">CoreClrDebugRuntimeInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="874df-102">CoreClrDebugRuntimeInfo Structure</span></span>

<span data-ttu-id="874df-103">Representa una instancia de Common Language Runtime (CLR) que se carga en un proceso en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="874df-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="874df-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="874df-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="874df-105">Members</span></span>  
  
|<span data-ttu-id="874df-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="874df-106">Member</span></span>|<span data-ttu-id="874df-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="874df-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="874df-108">Identificador en tiempo de ejecución asignado por el proxy de depuración remota en ejecución en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="874df-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="874df-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="874df-109">Requirements</span></span>  

 <span data-ttu-id="874df-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="874df-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="874df-111">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="874df-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="874df-112">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="874df-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="874df-113">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="874df-113">**.NET Framework Versions:** 3.5 SP1</span></span>
