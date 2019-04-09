---
title: PreCloseAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aab42e939651d75b1933962d72ba8bec1090f52d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184514"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="88489-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="88489-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="88489-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="88489-103">Closes the assembly file.</span></span> <span data-ttu-id="88489-104">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="88489-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="88489-105">No llame a este método para módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="88489-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88489-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88489-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="88489-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88489-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="88489-108">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="88489-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88489-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="88489-109">Return Value</span></span>  
 <span data-ttu-id="88489-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="88489-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88489-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88489-111">Requirements</span></span>  
 <span data-ttu-id="88489-112">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="88489-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88489-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="88489-113">See also</span></span>

- [<span data-ttu-id="88489-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88489-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="88489-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88489-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="88489-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="88489-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
