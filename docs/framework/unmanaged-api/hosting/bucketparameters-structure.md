---
title: BucketParameters (Estructura)
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 80623bdec939b0ae5fc13008c1c4001c613ac435
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195956"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="7c53f-102">BucketParameters (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7c53f-102">BucketParameters Structure</span></span>
<span data-ttu-id="7c53f-103">Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="7c53f-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c53f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c53f-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="7c53f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7c53f-105">Members</span></span>  
  
|<span data-ttu-id="7c53f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7c53f-106">Member</span></span>|<span data-ttu-id="7c53f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c53f-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="7c53f-108">`true`, si el resto de esta estructura es válido; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7c53f-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="7c53f-109">Nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="7c53f-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="7c53f-110">Matriz de cadenas, cada una de las cuales especifica un parámetro para la excepción actual asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="7c53f-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c53f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c53f-111">Requirements</span></span>  
 <span data-ttu-id="7c53f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c53f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c53f-113">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="7c53f-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="7c53f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c53f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c53f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c53f-115">See also</span></span>

- [<span data-ttu-id="7c53f-116">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7c53f-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
