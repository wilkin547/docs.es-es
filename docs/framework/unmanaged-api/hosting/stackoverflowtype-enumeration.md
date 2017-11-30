---
title: "StackOverflowType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackOverflowType
api_location: mscoree.dll
api_type: COM
f1_keywords: StackOverflowType
helpviewer_keywords: StackOverflowType enumeration [.NET Framework hosting]
ms.assetid: dab648ad-972b-479c-b129-b4c1dcbd932e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 64312398c95a33c2bbe136b1c4d03c06cb09aeef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="stackoverflowtype-enumeration"></a><span data-ttu-id="2ec9c-102">StackOverflowType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2ec9c-102">StackOverflowType Enumeration</span></span>
<span data-ttu-id="2ec9c-103">Contiene valores que indican la causa subyacente de un evento de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="2ec9c-103">Contains values that indicate the underlying cause of a stack overflow event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ec9c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ec9c-104">Syntax</span></span>  
  
```  
typedef enum {  
    SO_Managed,  
    SO_ClrEngine,  
    SO_Other  
} StackOverflowType;  
```  
  
## <a name="members"></a><span data-ttu-id="2ec9c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2ec9c-105">Members</span></span>  
  
|<span data-ttu-id="2ec9c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2ec9c-106">Member</span></span>|<span data-ttu-id="2ec9c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ec9c-107">Description</span></span>|  
|------------|-----------------|  
|`SO_ClrEngine`|<span data-ttu-id="2ec9c-108">El motor de ejecución produjo el desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="2ec9c-108">The stack overflow was caused by the execution engine.</span></span>|  
|`SO_Managed`|<span data-ttu-id="2ec9c-109">Código administrado produjo el desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="2ec9c-109">The stack overflow was caused by managed code.</span></span>|  
|`SO_Other`|<span data-ttu-id="2ec9c-110">Se produjo el desbordamiento de pila por código no administrado.</span><span class="sxs-lookup"><span data-stu-id="2ec9c-110">The stack overflow was caused by unmanaged code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec9c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2ec9c-111">Remarks</span></span>  
 <span data-ttu-id="2ec9c-112">Esta información se pasa al host a través de una llamada a la [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2ec9c-112">This information is passed to the host through a call to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ec9c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ec9c-113">Requirements</span></span>  
 <span data-ttu-id="2ec9c-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ec9c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ec9c-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ec9c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ec9c-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ec9c-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ec9c-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ec9c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec9c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ec9c-118">See Also</span></span>  
 [<span data-ttu-id="2ec9c-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="2ec9c-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
