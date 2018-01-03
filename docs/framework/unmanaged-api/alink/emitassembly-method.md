---
title: "EmitAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssembly
helpviewer_keywords: EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f012ea89fec0e64bc1639e6c47fb79249c25411a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="emitassembly-method"></a><span data-ttu-id="e6439-102">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="e6439-102">EmitAssembly Method</span></span>
<span data-ttu-id="e6439-103">Crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e6439-103">Creates the assembly.</span></span> <span data-ttu-id="e6439-104">Llamar a este método después de que se cierran todos los demás archivos excepto para el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e6439-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="e6439-105">No llame a este método al generar módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="e6439-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6439-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6439-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6439-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6439-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e6439-108">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e6439-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6439-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6439-109">Return Value</span></span>  
 <span data-ttu-id="e6439-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="e6439-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6439-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6439-111">Requirements</span></span>  
 <span data-ttu-id="e6439-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="e6439-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6439-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6439-113">See Also</span></span>  
 [<span data-ttu-id="e6439-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6439-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e6439-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6439-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e6439-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e6439-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
