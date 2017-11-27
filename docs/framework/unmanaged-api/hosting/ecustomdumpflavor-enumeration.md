---
title: "ECustomDumpFlavor (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ECustomDumpFlavor
api_location: mscoree.dll
api_type: COM
f1_keywords: ECustomDumpFlavor
helpviewer_keywords: ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a7317a3a12acef2a16deebab9a1e1b10205ebf6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="c6ede-102">ECustomDumpFlavor (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c6ede-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="c6ede-103">Contiene valores que indican qué elementos deben incluirse en un subconjunto personalizado de un montón de volcado de memoria al informar de errores.</span><span class="sxs-lookup"><span data-stu-id="c6ede-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ede-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6ede-104">Syntax</span></span>  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="c6ede-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c6ede-105">Members</span></span>  
  
|<span data-ttu-id="c6ede-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c6ede-106">Member</span></span>|<span data-ttu-id="c6ede-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6ede-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="c6ede-108">Especifica que el volcado del montón personalizado debe iniciarse como minivolcado e incluir datos adicionales especificados por cualquier [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) las instancias que se pasan al mismo método.</span><span class="sxs-lookup"><span data-stu-id="c6ede-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="c6ede-109">Especifica que el volcado del montón personalizado debe recopilar todos los datos de estado de tiempo de ejecución que no se asignan dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="c6ede-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6ede-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6ede-110">Remarks</span></span>  
 <span data-ttu-id="c6ede-111">Un parámetro de tipo `ECustomDumpFlavor` se pasa a la [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c6ede-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ede-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6ede-112">Requirements</span></span>  
 <span data-ttu-id="c6ede-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ede-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ede-114">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6ede-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6ede-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6ede-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6ede-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ede-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ede-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6ede-117">See Also</span></span>  
 [<span data-ttu-id="c6ede-118">ECustomDumpItemKind (enumeración)</span><span class="sxs-lookup"><span data-stu-id="c6ede-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="c6ede-119">ICLRErrorReportingManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6ede-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="c6ede-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="c6ede-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
