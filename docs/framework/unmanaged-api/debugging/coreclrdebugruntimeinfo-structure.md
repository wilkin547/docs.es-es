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
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860927"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="ae70a-102">CoreClrDebugRuntimeInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ae70a-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="ae70a-103">Representa una instancia de Common Language Runtime (CLR) que se carga en un proceso en un equipo remoto.</span><span class="sxs-lookup"><span data-stu-id="ae70a-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae70a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae70a-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="ae70a-105">Members</span><span class="sxs-lookup"><span data-stu-id="ae70a-105">Members</span></span>  
  
|<span data-ttu-id="ae70a-106">Member</span><span class="sxs-lookup"><span data-stu-id="ae70a-106">Member</span></span>|<span data-ttu-id="ae70a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae70a-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="ae70a-108">Identificador en tiempo de ejecución asignado por el proxy de depuración remota en ejecución en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="ae70a-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae70a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae70a-109">Requirements</span></span>  
 <span data-ttu-id="ae70a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae70a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae70a-111">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="ae70a-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ae70a-112">**Biblioteca:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="ae70a-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ae70a-113">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="ae70a-113">**.NET Framework Versions:** 3.5 SP1</span></span>
