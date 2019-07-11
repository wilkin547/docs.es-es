---
title: CloseAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 18e0b7b3547bb246588f6b255483d4c317e0df88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742229"
---
# <a name="closeassembly-method"></a><span data-ttu-id="e5743-102">CloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="e5743-102">CloseAssembly Method</span></span>
<span data-ttu-id="e5743-103">Finaliza las operaciones de montaje.</span><span class="sxs-lookup"><span data-stu-id="e5743-103">Finalizes assembly operations.</span></span> <span data-ttu-id="e5743-104">Llame a este método antes de comenzar un nuevo ensamblado o módulo no enlazado.</span><span class="sxs-lookup"><span data-stu-id="e5743-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5743-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5743-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5743-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5743-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e5743-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e5743-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5743-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5743-108">Return Value</span></span>  
 <span data-ttu-id="e5743-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="e5743-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5743-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5743-110">Requirements</span></span>  
 <span data-ttu-id="e5743-111">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="e5743-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5743-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5743-112">See also</span></span>

- [<span data-ttu-id="e5743-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5743-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e5743-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5743-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e5743-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e5743-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
