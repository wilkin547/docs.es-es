---
title: "EndMerge (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EndMerge
- EndMerge
api_location: alink.dll
api_type: COM
f1_keywords: EndMerge
helpviewer_keywords: EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f29abf03c636fc552fe550534ca1b1395b43aae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="endmerge-method"></a><span data-ttu-id="d93d7-102">EndMerge (Método)</span><span class="sxs-lookup"><span data-stu-id="d93d7-102">EndMerge Method</span></span>
<span data-ttu-id="d93d7-103">Indica que todos los atributos personalizados se han combinado en el ámbito de emisión.</span><span class="sxs-lookup"><span data-stu-id="d93d7-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d93d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d93d7-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d93d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d93d7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d93d7-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d93d7-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d93d7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d93d7-107">Return Value</span></span>  
 <span data-ttu-id="d93d7-108">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="d93d7-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d93d7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d93d7-109">Requirements</span></span>  
 <span data-ttu-id="d93d7-110">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="d93d7-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d93d7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d93d7-111">See Also</span></span>  
 [<span data-ttu-id="d93d7-112">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d93d7-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d93d7-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d93d7-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d93d7-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d93d7-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
