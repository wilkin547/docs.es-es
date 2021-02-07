---
description: 'Más información sobre: ICoreClrDebugTarget:: FreeMemory ((método)'
title: ICoreClrDebugTarget::FreeMemory (Método)
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: 9572e0c3df1fdd064e78ba170d39c1415c68dc85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690007"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="a2164-103">ICoreClrDebugTarget::FreeMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="a2164-103">ICoreClrDebugTarget::FreeMemory Method</span></span>

<span data-ttu-id="a2164-104">Libera la memoria asignada por los métodos [ICoreClrDebugTarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) y [ICoreClrDebugTarget:: enumruntimes (](icoreclrdebugtarget-enumruntimes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a2164-104">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2164-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2164-105">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2164-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2164-106">Parameters</span></span>  

 `pMemory`  
 <span data-ttu-id="a2164-107">de Puntero a la matriz devuelta por el método [ICoreClrDebugTarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) o [ICoreClrDebugTarget:: enumruntimes (](icoreclrdebugtarget-enumruntimes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a2164-107">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2164-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2164-108">Requirements</span></span>  

 <span data-ttu-id="a2164-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2164-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2164-110">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="a2164-110">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="a2164-111">**Biblioteca:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="a2164-111">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="a2164-112">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a2164-112">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2164-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2164-113">See also</span></span>

- [<span data-ttu-id="a2164-114">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2164-114">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
