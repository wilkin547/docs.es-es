---
title: "HOST_TYPE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: HOST_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: HOST_TYPE
helpviewer_keywords: HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8c910dd06109a8a69f29517812737d4b4dcef21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="hosttype-enumeration"></a><span data-ttu-id="2bdc4-102">HOST_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2bdc4-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="2bdc4-103">Contiene valores que especifican el tipo de host que está iniciando una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bdc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bdc4-104">Syntax</span></span>  
  
```  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="2bdc4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2bdc4-105">Members</span></span>  
  
|<span data-ttu-id="2bdc4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2bdc4-106">Member</span></span>|<span data-ttu-id="2bdc4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bdc4-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="2bdc4-108">Inicie la aplicación desde AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="2bdc4-109">Use este valor para aplicaciones de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="2bdc4-110">Inicie la aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-110">Launch the application directly.</span></span> <span data-ttu-id="2bdc4-111">Es decir, inicie la aplicación desde su propio archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="2bdc4-112">Use este valor para las aplicaciones de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="2bdc4-113">Igual que HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="2bdc4-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2bdc4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bdc4-114">Requirements</span></span>  
 <span data-ttu-id="2bdc4-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bdc4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bdc4-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2bdc4-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bdc4-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bdc4-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bdc4-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bdc4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bdc4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bdc4-119">See Also</span></span>  
 [<span data-ttu-id="2bdc4-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="2bdc4-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
