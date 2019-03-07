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
ms.openlocfilehash: c89fd080e61db78ed21c03c2aa63c97337c09585
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497553"
---
# <a name="closeassembly-method"></a><span data-ttu-id="82fab-102">CloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="82fab-102">CloseAssembly Method</span></span>
<span data-ttu-id="82fab-103">Finaliza las operaciones de montaje.</span><span class="sxs-lookup"><span data-stu-id="82fab-103">Finalizes assembly operations.</span></span> <span data-ttu-id="82fab-104">Llame a este método antes de comenzar un nuevo ensamblado o módulo no enlazado.</span><span class="sxs-lookup"><span data-stu-id="82fab-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82fab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82fab-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="82fab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82fab-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="82fab-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="82fab-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82fab-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82fab-108">Return Value</span></span>  
 <span data-ttu-id="82fab-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="82fab-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82fab-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82fab-110">Requirements</span></span>  
 <span data-ttu-id="82fab-111">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="82fab-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82fab-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="82fab-112">See also</span></span>
- [<span data-ttu-id="82fab-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82fab-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="82fab-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82fab-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="82fab-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="82fab-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
