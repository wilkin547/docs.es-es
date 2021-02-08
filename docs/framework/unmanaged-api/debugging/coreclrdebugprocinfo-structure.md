---
description: 'Más información acerca de: estructura Coreclrdebugprocinfo ('
title: CoreClrDebugProcInfo (Estructura)
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 04befb057be689e68dd3571a13990da9af64551f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801493"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="67295-103">CoreClrDebugProcInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="67295-103">CoreClrDebugProcInfo Structure</span></span>

<span data-ttu-id="67295-104">Representa un proceso que se ejecuta en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="67295-104">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67295-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67295-105">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="67295-106">Members</span><span class="sxs-lookup"><span data-stu-id="67295-106">Members</span></span>  
  
|<span data-ttu-id="67295-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="67295-107">Member</span></span>|<span data-ttu-id="67295-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="67295-108">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="67295-109">Identificador del proceso asignado por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="67295-109">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="67295-110">Identificador del proceso asignado por el proxy de depuración remota que se ejecuta en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="67295-110">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="67295-111">Este identificador se recicla con menos frecuencia que el identificador del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="67295-111">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="67295-112">Línea de comandos del proceso.</span><span class="sxs-lookup"><span data-stu-id="67295-112">Command-line of the process.</span></span> <span data-ttu-id="67295-113">Este miembro puede truncarse.</span><span class="sxs-lookup"><span data-stu-id="67295-113">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67295-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67295-114">Requirements</span></span>  

 <span data-ttu-id="67295-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67295-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67295-116">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="67295-116">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="67295-117">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="67295-117">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="67295-118">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="67295-118">**.NET Framework Versions:** 3.5 SP1</span></span>
