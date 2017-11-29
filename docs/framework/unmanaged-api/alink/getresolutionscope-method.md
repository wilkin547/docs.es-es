---
title: "GetResolutionScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetResolutionScope
api_location: alink.dll
api_type: COM
f1_keywords: GetResolutionScope
helpviewer_keywords: GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11ccbce4d8e9783514050f6b41c6e32cde6c274f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="1c9eb-102">GetResolutionScope (Método)</span><span class="sxs-lookup"><span data-stu-id="1c9eb-102">GetResolutionScope Method</span></span>
<span data-ttu-id="1c9eb-103">Recupera el ámbito de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="1c9eb-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c9eb-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c9eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c9eb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1c9eb-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1c9eb-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1c9eb-107">Archivo que necesita una referencia.</span><span class="sxs-lookup"><span data-stu-id="1c9eb-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="1c9eb-108">Símbolo (token) del archivo de ese tipo se define en la consulta, normalmente se recuperan con [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1c9eb-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="1c9eb-109">Recibe el ensamblado o una referencia al módulo.</span><span class="sxs-lookup"><span data-stu-id="1c9eb-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c9eb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1c9eb-110">Return Value</span></span>  
 <span data-ttu-id="1c9eb-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1c9eb-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c9eb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c9eb-112">Requirements</span></span>  
 <span data-ttu-id="1c9eb-113">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="1c9eb-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9eb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c9eb-114">See Also</span></span>  
 [<span data-ttu-id="1c9eb-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c9eb-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1c9eb-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c9eb-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1c9eb-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1c9eb-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
