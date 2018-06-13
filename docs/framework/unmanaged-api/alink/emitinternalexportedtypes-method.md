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
ms.openlocfilehash: 55b9d185804f25c7431f2696d67753cc3ba02d1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402046"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="b7c3f-102">EmitInternalExportedTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="b7c3f-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="b7c3f-103">Emite los tipos agregados al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-103">Emits types added to the assembly.</span></span> <span data-ttu-id="b7c3f-104">Llamar a este método después de que conoce los tipos internos se agregaron.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c3f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7c3f-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7c3f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7c3f-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b7c3f-107">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7c3f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7c3f-108">Return Value</span></span>  
 <span data-ttu-id="b7c3f-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="b7c3f-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7c3f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7c3f-110">Requirements</span></span>  
 <span data-ttu-id="b7c3f-111">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="b7c3f-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c3f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7c3f-112">See Also</span></span>  
 [<span data-ttu-id="b7c3f-113">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7c3f-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b7c3f-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7c3f-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b7c3f-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b7c3f-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
