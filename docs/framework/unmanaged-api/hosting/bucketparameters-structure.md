---
description: 'Más información acerca de: estructura Bucketparameters ('
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
ms.openlocfilehash: e2d701caa0e2374cb6b44d5fb5537f2ecc7e34fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799972"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="221d6-103">BucketParameters (Estructura)</span><span class="sxs-lookup"><span data-stu-id="221d6-103">BucketParameters Structure</span></span>

<span data-ttu-id="221d6-104">Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="221d6-104">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="221d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="221d6-105">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="221d6-106">Members</span><span class="sxs-lookup"><span data-stu-id="221d6-106">Members</span></span>  
  
|<span data-ttu-id="221d6-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="221d6-107">Member</span></span>|<span data-ttu-id="221d6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="221d6-108">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="221d6-109">`true`, si el resto de esta estructura es válido; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="221d6-109">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="221d6-110">Nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="221d6-110">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="221d6-111">Matriz de cadenas, cada una de las cuales especifica un parámetro para la excepción actual asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="221d6-111">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="221d6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="221d6-112">Requirements</span></span>  

 <span data-ttu-id="221d6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="221d6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="221d6-114">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="221d6-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="221d6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="221d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221d6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="221d6-116">See also</span></span>

- [<span data-ttu-id="221d6-117">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="221d6-117">Hosting Structures</span></span>](hosting-structures.md)
