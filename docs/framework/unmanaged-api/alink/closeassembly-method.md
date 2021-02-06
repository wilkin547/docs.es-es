---
description: 'Más información sobre: método Closeassembly ('
title: CloseAssembly (Método)
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
ms.openlocfilehash: 927a66f948f691c00a695c626d9c31950a722cb5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638397"
---
# <a name="closeassembly-method"></a><span data-ttu-id="f7842-103">CloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="f7842-103">CloseAssembly Method</span></span>

<span data-ttu-id="f7842-104">Finaliza las operaciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f7842-104">Finalizes assembly operations.</span></span> <span data-ttu-id="f7842-105">Llame a este método antes de iniciar un nuevo ensamblado o módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="f7842-105">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7842-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7842-106">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7842-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7842-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="f7842-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f7842-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7842-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7842-109">Return Value</span></span>  

 <span data-ttu-id="f7842-110">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7842-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7842-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7842-111">Requirements</span></span>  

 <span data-ttu-id="f7842-112">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="f7842-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7842-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7842-113">See also</span></span>

- [<span data-ttu-id="f7842-114">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7842-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f7842-115">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7842-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f7842-116">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f7842-116">ALink API</span></span>](index.md)
