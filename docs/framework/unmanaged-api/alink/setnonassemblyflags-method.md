---
description: 'Más información sobre: método Setnonassemblyflags ('
title: SetNonAssemblyFlags (Método)
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
ms.openlocfilehash: 9cf311ec8f04f97da03be626e20c1c07065eac38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662317"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="f277d-103">SetNonAssemblyFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="f277d-103">SetNonAssemblyFlags Method</span></span>

<span data-ttu-id="f277d-104">Establece marcas que no son específicas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f277d-104">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f277d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f277d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f277d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f277d-106">Parameters</span></span>  

 `afFlags`  
 <span data-ttu-id="f277d-107">Marcas de ALink.</span><span class="sxs-lookup"><span data-stu-id="f277d-107">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f277d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f277d-108">Return Value</span></span>  

 <span data-ttu-id="f277d-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f277d-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f277d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f277d-110">Requirements</span></span>  

 <span data-ttu-id="f277d-111">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="f277d-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f277d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f277d-112">See also</span></span>

- [<span data-ttu-id="f277d-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f277d-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f277d-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f277d-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f277d-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f277d-115">ALink API</span></span>](index.md)
