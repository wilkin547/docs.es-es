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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697867"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="339fc-102">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="339fc-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="339fc-103">Incluye el [ProvideLibrary (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de la biblioteca de interfaz de devolución de llamada que permite a common language runtime bibliotecas de depuración específica de la versión a buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="339fc-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="339fc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="339fc-104">Methods</span></span>  
  
|<span data-ttu-id="339fc-105">Método</span><span class="sxs-lookup"><span data-stu-id="339fc-105">Method</span></span>|<span data-ttu-id="339fc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="339fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="339fc-107">ProvideLibrary (método)</span><span class="sxs-lookup"><span data-stu-id="339fc-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="339fc-108">Permite al depurador proporcionar un identificador para un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="339fc-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="339fc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="339fc-109">Requirements</span></span>  
 <span data-ttu-id="339fc-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="339fc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="339fc-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="339fc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="339fc-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="339fc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="339fc-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="339fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="339fc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="339fc-114">See also</span></span>

- [<span data-ttu-id="339fc-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="339fc-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="339fc-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="339fc-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
