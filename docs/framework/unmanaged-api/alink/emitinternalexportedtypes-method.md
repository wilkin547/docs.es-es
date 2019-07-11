---
title: EmitInternalExportedTypes (Método)
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15174480c4345f2514572701a5525f0f192ad120
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742102"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="e7c56-102">EmitInternalExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="e7c56-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="e7c56-103">Emite los tipos agregados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7c56-103">Emits types added to the assembly.</span></span> <span data-ttu-id="e7c56-104">Llame a este método después de que conoce los tipos internos se han agregado.</span><span class="sxs-lookup"><span data-stu-id="e7c56-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c56-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7c56-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7c56-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7c56-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e7c56-107">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e7c56-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7c56-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e7c56-108">Return Value</span></span>  
 <span data-ttu-id="e7c56-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="e7c56-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c56-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7c56-110">Requirements</span></span>  
 <span data-ttu-id="e7c56-111">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="e7c56-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c56-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7c56-112">See also</span></span>

- [<span data-ttu-id="e7c56-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7c56-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e7c56-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7c56-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e7c56-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e7c56-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
