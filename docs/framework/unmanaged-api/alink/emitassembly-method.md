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
ms.openlocfilehash: 6bbe5db75ded15f32a6ff3564e1116d40a745a65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446522"
---
# <a name="emitassembly-method"></a><span data-ttu-id="02d00-102">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="02d00-102">EmitAssembly Method</span></span>
<span data-ttu-id="02d00-103">Creates the assembly.</span><span class="sxs-lookup"><span data-stu-id="02d00-103">Creates the assembly.</span></span> <span data-ttu-id="02d00-104">Call this method after all other files are closed except for the assembly file.</span><span class="sxs-lookup"><span data-stu-id="02d00-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="02d00-105">Do not call this method when producing unbound modules.</span><span class="sxs-lookup"><span data-stu-id="02d00-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d00-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02d00-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d00-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02d00-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="02d00-108">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="02d00-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02d00-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="02d00-109">Return Value</span></span>  
 <span data-ttu-id="02d00-110">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="02d00-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d00-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02d00-111">Requirements</span></span>  
 <span data-ttu-id="02d00-112">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="02d00-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d00-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d00-113">See also</span></span>

- [<span data-ttu-id="02d00-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02d00-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="02d00-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02d00-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="02d00-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="02d00-116">ALink API</span></span>](index.md)
