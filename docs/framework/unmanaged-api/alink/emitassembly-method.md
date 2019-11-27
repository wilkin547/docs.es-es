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
# <a name="emitassembly-method"></a><span data-ttu-id="a844d-102">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="a844d-102">EmitAssembly Method</span></span>
<span data-ttu-id="a844d-103">Crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a844d-103">Creates the assembly.</span></span> <span data-ttu-id="a844d-104">Llame a este método después de que se cierren todos los demás archivos excepto el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a844d-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="a844d-105">No llame a este método al producir módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="a844d-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a844d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a844d-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a844d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a844d-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a844d-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a844d-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a844d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a844d-109">Return Value</span></span>  
 <span data-ttu-id="a844d-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="a844d-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a844d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a844d-111">Requirements</span></span>  
 <span data-ttu-id="a844d-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="a844d-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a844d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a844d-113">See also</span></span>

- [<span data-ttu-id="a844d-114">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a844d-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a844d-115">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a844d-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a844d-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a844d-116">ALink API</span></span>](index.md)
