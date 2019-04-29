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
ms.openlocfilehash: 94c1c083d010cd82fd9e9e2f02b23e81d88fedd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790096"
---
# <a name="closeassembly-method"></a><span data-ttu-id="69dbd-102">CloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="69dbd-102">CloseAssembly Method</span></span>
<span data-ttu-id="69dbd-103">Finaliza las operaciones de montaje.</span><span class="sxs-lookup"><span data-stu-id="69dbd-103">Finalizes assembly operations.</span></span> <span data-ttu-id="69dbd-104">Llame a este método antes de comenzar un nuevo ensamblado o módulo no enlazado.</span><span class="sxs-lookup"><span data-stu-id="69dbd-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69dbd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69dbd-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="69dbd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69dbd-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="69dbd-107">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="69dbd-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69dbd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69dbd-108">Return Value</span></span>  
 <span data-ttu-id="69dbd-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="69dbd-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69dbd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69dbd-110">Requirements</span></span>  
 <span data-ttu-id="69dbd-111">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="69dbd-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dbd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="69dbd-112">See also</span></span>

- [<span data-ttu-id="69dbd-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69dbd-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="69dbd-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69dbd-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="69dbd-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="69dbd-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
