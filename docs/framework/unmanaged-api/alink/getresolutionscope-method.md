---
title: GetResolutionScope (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6c2e741df594e265fdef51a602a9a4927733b7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741865"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="9c8e2-102">GetResolutionScope (Método)</span><span class="sxs-lookup"><span data-stu-id="9c8e2-102">GetResolutionScope Method</span></span>
<span data-ttu-id="9c8e2-103">Recupera el ámbito de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="9c8e2-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c8e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c8e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c8e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c8e2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9c8e2-106">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9c8e2-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9c8e2-107">Archivo que necesita una referencia.</span><span class="sxs-lookup"><span data-stu-id="9c8e2-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="9c8e2-108">Token del archivo de ese tipo se define en la consulta, normalmente se recuperan con [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c8e2-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="9c8e2-109">Recibe el ensamblado o una referencia de módulo.</span><span class="sxs-lookup"><span data-stu-id="9c8e2-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c8e2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9c8e2-110">Return Value</span></span>  
 <span data-ttu-id="9c8e2-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="9c8e2-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c8e2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c8e2-112">Requirements</span></span>  
 <span data-ttu-id="9c8e2-113">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="9c8e2-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c8e2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c8e2-114">See also</span></span>

- [<span data-ttu-id="9c8e2-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c8e2-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9c8e2-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c8e2-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9c8e2-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9c8e2-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
