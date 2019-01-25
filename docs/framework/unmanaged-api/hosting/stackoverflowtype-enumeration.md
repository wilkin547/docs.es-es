---
title: StackOverflowType (Enumeración)
ms.date: 03/30/2017
api_name:
- StackOverflowType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowType
helpviewer_keywords:
- StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06c9119a2b842a0efcd4af752ba72dbfda03bf13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653871"
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="1ef80-102">StackOverflowType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1ef80-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="1ef80-103">Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="1ef80-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ef80-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="1ef80-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1ef80-105">Members</span></span>  
  
|<span data-ttu-id="1ef80-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1ef80-106">Member</span></span>|<span data-ttu-id="1ef80-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ef80-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="1ef80-108">El desbordamiento de pila fue causado por el motor de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ef80-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="1ef80-109">El desbordamiento de pila se debió a código administrado.</span><span class="sxs-lookup"><span data-stu-id="1ef80-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="1ef80-110">El desbordamiento de pila se debió a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="1ef80-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ef80-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ef80-111">Remarks</span></span>  
 <span data-ttu-id="1ef80-112">Esta información se pasa al host mediante una llamada a la [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1ef80-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef80-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ef80-113">Requirements</span></span>  
 <span data-ttu-id="1ef80-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ef80-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef80-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ef80-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ef80-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ef80-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ef80-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef80-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef80-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ef80-118">See also</span></span>
- [<span data-ttu-id="1ef80-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="1ef80-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
