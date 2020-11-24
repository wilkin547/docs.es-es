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
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677861"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="d7f73-102">BucketParameters (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d7f73-102">BucketParameters Structure</span></span>

<span data-ttu-id="d7f73-103">Almacena el nombre de tipo de un evento y los parámetros de la excepción actual que está asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="d7f73-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7f73-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="d7f73-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d7f73-105">Members</span></span>  
  
|<span data-ttu-id="d7f73-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d7f73-106">Member</span></span>|<span data-ttu-id="d7f73-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7f73-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="d7f73-108">`true`, si el resto de esta estructura es válido; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d7f73-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="d7f73-109">Nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="d7f73-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="d7f73-110">Matriz de cadenas, cada una de las cuales especifica un parámetro para la excepción actual asociada al evento.</span><span class="sxs-lookup"><span data-stu-id="d7f73-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7f73-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7f73-111">Requirements</span></span>  

 <span data-ttu-id="d7f73-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f73-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f73-113">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="d7f73-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d7f73-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f73-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7f73-115">See also</span></span>

- [<span data-ttu-id="d7f73-116">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d7f73-116">Hosting Structures</span></span>](hosting-structures.md)
