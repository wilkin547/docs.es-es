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
ms.openlocfilehash: c62079a87c09bcbe09167a137fd39530652ae3e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106345"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="ad397-102">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad397-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="ad397-103">Incluye el [ProvideLibrary (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de la biblioteca de interfaz de devolución de llamada que permite a common language runtime bibliotecas de depuración específica de la versión a buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="ad397-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad397-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad397-104">Methods</span></span>  
  
|<span data-ttu-id="ad397-105">Método</span><span class="sxs-lookup"><span data-stu-id="ad397-105">Method</span></span>|<span data-ttu-id="ad397-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad397-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad397-107">Método ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="ad397-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="ad397-108">Permite al depurador proporcionar un identificador para un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="ad397-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad397-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad397-109">Requirements</span></span>  
 <span data-ttu-id="ad397-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad397-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad397-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad397-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad397-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad397-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ad397-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ad397-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad397-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad397-114">See also</span></span>

- [<span data-ttu-id="ad397-115">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ad397-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ad397-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="ad397-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
