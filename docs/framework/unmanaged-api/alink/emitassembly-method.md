---
title: EmitAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf7b54ab7a2318e8194bf39dbe41b864633ddb43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212917"
---
# <a name="emitassembly-method"></a><span data-ttu-id="19af9-102">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="19af9-102">EmitAssembly Method</span></span>
<span data-ttu-id="19af9-103">Crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19af9-103">Creates the assembly.</span></span> <span data-ttu-id="19af9-104">Llame a este método después de que todos los demás archivos se cierran, excepto el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19af9-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="19af9-105">No llame a este método cuando se producen los módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="19af9-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19af9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19af9-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="19af9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19af9-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="19af9-108">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="19af9-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19af9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="19af9-109">Return Value</span></span>  
 <span data-ttu-id="19af9-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="19af9-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19af9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19af9-111">Requirements</span></span>  
 <span data-ttu-id="19af9-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="19af9-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19af9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="19af9-113">See also</span></span>

- [<span data-ttu-id="19af9-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19af9-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="19af9-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="19af9-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="19af9-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="19af9-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
