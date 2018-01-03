---
title: "PreCloseAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.PreCloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: PreCloseAssembly
helpviewer_keywords: PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a4d1f2eed036552ab17b6768b7b2d84f4a52c9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="precloseassembly-method"></a><span data-ttu-id="79494-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="79494-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="79494-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="79494-103">Closes the assembly file.</span></span> <span data-ttu-id="79494-104">Llamar a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="79494-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="79494-105">No llame a este método para módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="79494-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79494-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79494-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79494-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79494-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="79494-108">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="79494-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79494-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79494-109">Return Value</span></span>  
 <span data-ttu-id="79494-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="79494-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79494-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79494-111">Requirements</span></span>  
 <span data-ttu-id="79494-112">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="79494-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79494-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="79494-113">See Also</span></span>  
 [<span data-ttu-id="79494-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79494-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="79494-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79494-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="79494-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="79494-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
