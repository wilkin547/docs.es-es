---
description: 'Más información acerca de: enumeración HOST_TYPE'
title: HOST_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 6a0baf3050f99885953ddec06342cbe19accfef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785242"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="4cc04-103">HOST_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4cc04-103">HOST_TYPE Enumeration</span></span>

<span data-ttu-id="4cc04-104">Contiene valores que especifican el tipo de host que está iniciando una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cc04-104">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc04-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cc04-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="4cc04-106">Members</span><span class="sxs-lookup"><span data-stu-id="4cc04-106">Members</span></span>  
  
|<span data-ttu-id="4cc04-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="4cc04-107">Member</span></span>|<span data-ttu-id="4cc04-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4cc04-108">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="4cc04-109">Inicie la aplicación desde AppLaunch.exe.</span><span class="sxs-lookup"><span data-stu-id="4cc04-109">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="4cc04-110">Use este valor para las aplicaciones de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="4cc04-110">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="4cc04-111">Inicie la aplicación directamente.</span><span class="sxs-lookup"><span data-stu-id="4cc04-111">Launch the application directly.</span></span> <span data-ttu-id="4cc04-112">Es decir, inicie la aplicación desde su propio archivo. exe.</span><span class="sxs-lookup"><span data-stu-id="4cc04-112">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="4cc04-113">Use este valor para las aplicaciones de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="4cc04-113">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="4cc04-114">Igual que HOST_TYPE_APPLAUNCH.</span><span class="sxs-lookup"><span data-stu-id="4cc04-114">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4cc04-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cc04-115">Requirements</span></span>  

 <span data-ttu-id="4cc04-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cc04-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cc04-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4cc04-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cc04-118">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4cc04-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cc04-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc04-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc04-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cc04-120">See also</span></span>

- [<span data-ttu-id="4cc04-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="4cc04-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
