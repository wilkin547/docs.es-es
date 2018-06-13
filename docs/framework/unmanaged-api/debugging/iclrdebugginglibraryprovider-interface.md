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
ms.openlocfilehash: 7537d3d6f741f36ab81d73751963a8539de0a36c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404474"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="e5a9b-102">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5a9b-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="e5a9b-103">Incluye el [ProvideLibrary (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de bibliotecas de interfaz de devolución de llamada que permite a common language bibliotecas de depuración específicas de la versión en tiempo de ejecución buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5a9b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e5a9b-104">Methods</span></span>  
  
|<span data-ttu-id="e5a9b-105">Método</span><span class="sxs-lookup"><span data-stu-id="e5a9b-105">Method</span></span>|<span data-ttu-id="e5a9b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5a9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5a9b-107">ProvideLibrary (método)</span><span class="sxs-lookup"><span data-stu-id="e5a9b-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="e5a9b-108">Permite al depurador proporcionar un identificador para un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="e5a9b-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5a9b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5a9b-109">Requirements</span></span>  
 <span data-ttu-id="e5a9b-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5a9b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a9b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5a9b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5a9b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5a9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5a9b-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a9b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a9b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5a9b-114">See Also</span></span>  
 [<span data-ttu-id="e5a9b-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e5a9b-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e5a9b-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="e5a9b-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
