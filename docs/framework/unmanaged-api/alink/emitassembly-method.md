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
ms.openlocfilehash: d73c158fa9d7b5574e4f875b8d51e932e30041b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572245"
---
# <a name="emitassembly-method"></a><span data-ttu-id="3f83c-102">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="3f83c-102">EmitAssembly Method</span></span>
<span data-ttu-id="3f83c-103">Crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3f83c-103">Creates the assembly.</span></span> <span data-ttu-id="3f83c-104">Llame a este método después de que todos los demás archivos se cierran, excepto el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3f83c-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="3f83c-105">No llame a este método cuando se producen los módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="3f83c-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f83c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f83c-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f83c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f83c-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3f83c-108">Id. del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3f83c-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f83c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3f83c-109">Return Value</span></span>  
 <span data-ttu-id="3f83c-110">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="3f83c-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f83c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f83c-111">Requirements</span></span>  
 <span data-ttu-id="3f83c-112">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="3f83c-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f83c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f83c-113">See also</span></span>
- [<span data-ttu-id="3f83c-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f83c-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3f83c-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f83c-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3f83c-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="3f83c-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
