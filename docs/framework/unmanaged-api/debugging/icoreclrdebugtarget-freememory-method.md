---
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
ms.openlocfilehash: 061a2b9990d4b4d6398d0a31b97bc403a5f10de4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397171"
---
# <a name="icoreclrdebugtargetfreememory-method"></a><span data-ttu-id="8fd29-102">ICoreClrDebugTarget::FreeMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="8fd29-102">ICoreClrDebugTarget::FreeMemory Method</span></span>
<span data-ttu-id="8fd29-103">Libera la memoria asignada por los métodos [ICoreClrDebugTarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) y [ICoreClrDebugTarget:: enumruntimes (](icoreclrdebugtarget-enumruntimes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8fd29-103">Frees the memory allocated by the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) and [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fd29-104">Syntax</span></span>  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fd29-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8fd29-105">Parameters</span></span>  
 `pMemory`  
 <span data-ttu-id="8fd29-106">de Puntero a la matriz devuelta por el método [ICoreClrDebugTarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) o [ICoreClrDebugTarget:: enumruntimes (](icoreclrdebugtarget-enumruntimes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8fd29-106">[in] A pointer to the array that is returned by either the [ICoreClrDebugTarget::EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) or the [ICoreClrDebugTarget::EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd29-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fd29-107">Requirements</span></span>  
 <span data-ttu-id="8fd29-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fd29-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd29-109">**Encabezado:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="8fd29-109">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8fd29-110">**Biblioteca:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="8fd29-110">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8fd29-111">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="8fd29-111">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd29-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fd29-112">See also</span></span>

- [<span data-ttu-id="8fd29-113">ICoreClrDebugTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fd29-113">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)
