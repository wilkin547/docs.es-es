---
description: 'Más información acerca de: interfaz ICLRDebuggingLibraryProvider ('
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
ms.openlocfilehash: 8aaec87e97d45c8b7b6f87aee64154ea3f48b133
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723288"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="64a76-103">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64a76-103">ICLRDebuggingLibraryProvider Interface</span></span>

<span data-ttu-id="64a76-104">Incluye el método del [método ProvideLibrary (](iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="64a76-104">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64a76-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="64a76-105">Methods</span></span>  
  
|<span data-ttu-id="64a76-106">Método</span><span class="sxs-lookup"><span data-stu-id="64a76-106">Method</span></span>|<span data-ttu-id="64a76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="64a76-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64a76-108">Método ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="64a76-108">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="64a76-109">Permite al depurador proporcionar un identificador a un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="64a76-109">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64a76-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64a76-110">Requirements</span></span>  

 <span data-ttu-id="64a76-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64a76-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a76-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64a76-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64a76-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64a76-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64a76-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a76-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a76-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="64a76-115">See also</span></span>

- [<span data-ttu-id="64a76-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="64a76-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="64a76-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="64a76-117">Debugging</span></span>](index.md)
