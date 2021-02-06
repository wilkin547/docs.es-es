---
description: 'Más información acerca de: EmitAssembly (método)'
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
ms.openlocfilehash: aada17d8df6435c5edfe6beb5db5ee13f887f253
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638345"
---
# <a name="emitassembly-method"></a><span data-ttu-id="75400-103">EmitAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="75400-103">EmitAssembly Method</span></span>

<span data-ttu-id="75400-104">Crea el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="75400-104">Creates the assembly.</span></span> <span data-ttu-id="75400-105">Llame a este método después de que se cierren todos los demás archivos excepto el archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="75400-105">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="75400-106">No llame a este método al producir módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="75400-106">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75400-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75400-107">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="75400-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75400-108">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="75400-109">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="75400-109">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75400-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75400-110">Return Value</span></span>  

 <span data-ttu-id="75400-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="75400-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75400-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75400-112">Requirements</span></span>  

 <span data-ttu-id="75400-113">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="75400-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75400-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="75400-114">See also</span></span>

- [<span data-ttu-id="75400-115">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75400-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="75400-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75400-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="75400-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="75400-117">ALink API</span></span>](index.md)
