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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753470"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="42ec9-102">PreCloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="42ec9-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="42ec9-103">Cierra el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42ec9-103">Closes the assembly file.</span></span> <span data-ttu-id="42ec9-104">Llame a este método después de cerrar todos los demás archivos, pero antes de cerrar el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42ec9-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="42ec9-105">No llame a este método para módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="42ec9-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ec9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42ec9-106">Syntax</span></span>  
  
```  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ec9-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42ec9-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="42ec9-108">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="42ec9-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42ec9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42ec9-109">Return Value</span></span>  
 <span data-ttu-id="42ec9-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="42ec9-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ec9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42ec9-111">Requirements</span></span>  
 <span data-ttu-id="42ec9-112">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="42ec9-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ec9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="42ec9-113">See also</span></span>

- [<span data-ttu-id="42ec9-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ec9-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="42ec9-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42ec9-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="42ec9-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="42ec9-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
