---
description: 'Más información sobre: enumeración Ecustomdumpflavor ('
title: ECustomDumpFlavor (Enumeración)
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 3ef118368fc827472bdaacb0b03d8c2011275056
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785538"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="7a8d4-103">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7a8d4-103">ECustomDumpFlavor Enumeration</span></span>

<span data-ttu-id="7a8d4-104">Contiene valores que indican qué elementos se van a incluir en un subconjunto personalizado de un volcado del montón cuando se notifican errores.</span><span class="sxs-lookup"><span data-stu-id="7a8d4-104">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8d4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a8d4-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="7a8d4-106">Members</span><span class="sxs-lookup"><span data-stu-id="7a8d4-106">Members</span></span>  
  
|<span data-ttu-id="7a8d4-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7a8d4-107">Member</span></span>|<span data-ttu-id="7a8d4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a8d4-108">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="7a8d4-109">Especifica que el volcado del montón personalizado debe iniciarse como minivolcado e incluir los datos adicionales especificados por las instancias de [customdumpitem (](customdumpitem-structure.md) que se hayan pasado al mismo método.</span><span class="sxs-lookup"><span data-stu-id="7a8d4-109">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="7a8d4-110">Especifica que el volcado del montón personalizado debe recopilar todos los datos de estado de tiempo de ejecución que no se asignaron dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="7a8d4-110">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a8d4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7a8d4-111">Remarks</span></span>  

 <span data-ttu-id="7a8d4-112">Un parámetro de tipo `ECustomDumpFlavor` se pasa al método [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7a8d4-112">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8d4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a8d4-113">Requirements</span></span>  

 <span data-ttu-id="7a8d4-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a8d4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8d4-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7a8d4-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a8d4-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a8d4-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a8d4-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a8d4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8d4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a8d4-118">See also</span></span>

- [<span data-ttu-id="7a8d4-119">ECustomDumpItemKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7a8d4-119">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="7a8d4-120">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a8d4-120">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="7a8d4-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="7a8d4-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
