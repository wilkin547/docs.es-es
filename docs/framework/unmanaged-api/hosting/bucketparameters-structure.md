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
ms.openlocfilehash: 7037065be138c369b847e7f86de7b46fc5ae601a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616884"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="e1ecb-102">BucketParameters (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e1ecb-102">BucketParameters Structure</span></span>
<span data-ttu-id="e1ecb-103">Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="e1ecb-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ecb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1ecb-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="e1ecb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e1ecb-105">Members</span></span>  
  
|<span data-ttu-id="e1ecb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e1ecb-106">Member</span></span>|<span data-ttu-id="e1ecb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1ecb-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="e1ecb-108">`true`, si el resto de esta estructura es válido; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e1ecb-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="e1ecb-109">Nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="e1ecb-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="e1ecb-110">Matriz de cadenas, cada una de las cuales especifica un parámetro para la excepción actual asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="e1ecb-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1ecb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1ecb-111">Requirements</span></span>  
 <span data-ttu-id="e1ecb-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1ecb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ecb-113">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="e1ecb-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e1ecb-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ecb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ecb-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="e1ecb-115">See also</span></span>

- [<span data-ttu-id="e1ecb-116">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e1ecb-116">Hosting Structures</span></span>](hosting-structures.md)
