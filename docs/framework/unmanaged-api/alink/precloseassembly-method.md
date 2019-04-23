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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184514"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="d626c-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d626c-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="d626c-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d626c-103">Closes the assembly file.</span></span> <span data-ttu-id="d626c-104">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d626c-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="d626c-105">No llame a este método para módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="d626c-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d626c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d626c-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d626c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d626c-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="d626c-108">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d626c-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d626c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d626c-109">Return Value</span></span>  
 <span data-ttu-id="d626c-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="d626c-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d626c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d626c-111">Requirements</span></span>  
 <span data-ttu-id="d626c-112">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="d626c-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d626c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d626c-113">See also</span></span>

- [<span data-ttu-id="d626c-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d626c-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d626c-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d626c-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d626c-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d626c-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
