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
ms.openlocfilehash: 77c2011ce677d1bd2823d47740782f48151b408a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860283"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="a0713-102">ICLRDebuggingLibraryProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0713-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="a0713-103">Incluye el método del [método ProvideLibrary (](iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a0713-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0713-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a0713-104">Methods</span></span>  
  
|<span data-ttu-id="a0713-105">Método</span><span class="sxs-lookup"><span data-stu-id="a0713-105">Method</span></span>|<span data-ttu-id="a0713-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0713-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0713-107">Método ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="a0713-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="a0713-108">Permite al depurador proporcionar un identificador a un módulo que se puede usar para cargar una biblioteca de depuración.</span><span class="sxs-lookup"><span data-stu-id="a0713-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0713-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0713-109">Requirements</span></span>  
 <span data-ttu-id="a0713-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0713-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0713-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0713-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0713-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0713-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0713-113">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0713-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0713-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0713-114">See also</span></span>

- [<span data-ttu-id="a0713-115">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a0713-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a0713-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="a0713-116">Debugging</span></span>](index.md)
