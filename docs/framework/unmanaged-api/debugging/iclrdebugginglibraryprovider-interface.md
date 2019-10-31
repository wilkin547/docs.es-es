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
ms.openlocfilehash: 81b9ffe5979ad553a5bdfbc27111469b2ff4db6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111376"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="54076-102">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="54076-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="54076-103">Incluye el método del [método ProvideLibrary (](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="54076-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54076-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="54076-104">Methods</span></span>  
  
|<span data-ttu-id="54076-105">Método</span><span class="sxs-lookup"><span data-stu-id="54076-105">Method</span></span>|<span data-ttu-id="54076-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="54076-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54076-107">ProvideLibrary (método)</span><span class="sxs-lookup"><span data-stu-id="54076-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="54076-108">Permite al depurador proporcionar un identificador a un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="54076-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54076-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54076-109">Requirements</span></span>  
 <span data-ttu-id="54076-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54076-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54076-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54076-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54076-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54076-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54076-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54076-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54076-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="54076-114">See also</span></span>

- [<span data-ttu-id="54076-115">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="54076-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="54076-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="54076-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
