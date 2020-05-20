---
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
ms.openlocfilehash: 9b4c1187945b4c243375a3096c3a8a3b22599aef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616286"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="0f0a1-102">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0f0a1-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="0f0a1-103">Contiene valores que indican qué elementos se van a incluir en un subconjunto personalizado de un volcado del montón cuando se notifican errores.</span><span class="sxs-lookup"><span data-stu-id="0f0a1-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f0a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f0a1-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="0f0a1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0f0a1-105">Members</span></span>  
  
|<span data-ttu-id="0f0a1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0f0a1-106">Member</span></span>|<span data-ttu-id="0f0a1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f0a1-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="0f0a1-108">Especifica que el volcado del montón personalizado debe iniciarse como minivolcado e incluir los datos adicionales especificados por las instancias de [customdumpitem (](customdumpitem-structure.md) que se hayan pasado al mismo método.</span><span class="sxs-lookup"><span data-stu-id="0f0a1-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="0f0a1-109">Especifica que el volcado del montón personalizado debe recopilar todos los datos de estado de tiempo de ejecución que no se asignaron dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="0f0a1-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f0a1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f0a1-110">Remarks</span></span>  
 <span data-ttu-id="0f0a1-111">Un parámetro de tipo `ECustomDumpFlavor` se pasa al método [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0f0a1-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f0a1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f0a1-112">Requirements</span></span>  
 <span data-ttu-id="0f0a1-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f0a1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f0a1-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0f0a1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f0a1-115">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0f0a1-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f0a1-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f0a1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0a1-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0f0a1-117">See also</span></span>

- [<span data-ttu-id="0f0a1-118">ECustomDumpItemKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0f0a1-118">ECustomDumpItemKind Enumeration</span></span>](ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="0f0a1-119">ICLRErrorReportingManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f0a1-119">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="0f0a1-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="0f0a1-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
