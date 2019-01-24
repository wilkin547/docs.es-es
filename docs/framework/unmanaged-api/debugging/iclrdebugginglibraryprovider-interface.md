---
title: ICLRDebuggingLibraryProvider (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d851a31cbbf429f49b9f369ce9bc03fa110b5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731990"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="271ce-102">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="271ce-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="271ce-103">Incluye el [ProvideLibrary (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de la biblioteca de interfaz de devolución de llamada que permite a common language runtime bibliotecas de depuración específica de la versión a buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="271ce-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="271ce-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="271ce-104">Methods</span></span>  
  
|<span data-ttu-id="271ce-105">Método</span><span class="sxs-lookup"><span data-stu-id="271ce-105">Method</span></span>|<span data-ttu-id="271ce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="271ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="271ce-107">ProvideLibrary (método)</span><span class="sxs-lookup"><span data-stu-id="271ce-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="271ce-108">Permite al depurador proporcionar un identificador para un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="271ce-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="271ce-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="271ce-109">Requirements</span></span>  
 <span data-ttu-id="271ce-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="271ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="271ce-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="271ce-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="271ce-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="271ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="271ce-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="271ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271ce-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="271ce-114">See also</span></span>
- [<span data-ttu-id="271ce-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="271ce-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="271ce-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="271ce-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
