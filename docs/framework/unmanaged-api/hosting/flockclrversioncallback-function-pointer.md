---
title: puntero a la función FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c884d07fa35c053b1a3b65c04426ac0e3712621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429678"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="53e1b-102">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="53e1b-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="53e1b-103">Señala a una función que las llamadas de runtime (CLR) de lenguaje común para indicar que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="53e1b-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="53e1b-104">Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53e1b-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53e1b-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="53e1b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53e1b-106">Remarks</span></span>  
 <span data-ttu-id="53e1b-107">Esta función es implementada por el host.</span><span class="sxs-lookup"><span data-stu-id="53e1b-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53e1b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53e1b-108">Requirements</span></span>  
 <span data-ttu-id="53e1b-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53e1b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e1b-110">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53e1b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53e1b-111">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="53e1b-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="53e1b-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e1b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e1b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="53e1b-113">See Also</span></span>  
 [<span data-ttu-id="53e1b-114">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="53e1b-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 [<span data-ttu-id="53e1b-115">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="53e1b-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
