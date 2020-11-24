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
ms.openlocfilehash: b85b2576660f77eb901c504d398e8bc7909882f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676379"
---
# <a name="emitassembly-method"></a><span data-ttu-id="90b3b-102">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="90b3b-102">EmitAssembly Method</span></span>

<span data-ttu-id="90b3b-103">Crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90b3b-103">Creates the assembly.</span></span> <span data-ttu-id="90b3b-104">Llame a este método después de que se cierren todos los demás archivos excepto el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90b3b-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="90b3b-105">No llame a este método al producir módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="90b3b-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b3b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90b3b-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="90b3b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90b3b-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="90b3b-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90b3b-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90b3b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90b3b-109">Return Value</span></span>  

 <span data-ttu-id="90b3b-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="90b3b-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90b3b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90b3b-111">Requirements</span></span>  

 <span data-ttu-id="90b3b-112">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="90b3b-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b3b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90b3b-113">See also</span></span>

- [<span data-ttu-id="90b3b-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90b3b-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="90b3b-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90b3b-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="90b3b-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="90b3b-116">ALink API</span></span>](index.md)
