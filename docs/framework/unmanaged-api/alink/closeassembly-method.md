---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7828c86018724bb934de99cab4617f9885fdca6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787606"
---
# <a name="closeassembly-method"></a><span data-ttu-id="71b6e-102">CloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="71b6e-102">CloseAssembly Method</span></span>
<span data-ttu-id="71b6e-103">Finaliza las operaciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="71b6e-103">Finalizes assembly operations.</span></span> <span data-ttu-id="71b6e-104">Llame a este método antes de iniciar un nuevo ensamblado o módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="71b6e-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b6e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71b6e-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="71b6e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71b6e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="71b6e-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="71b6e-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71b6e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71b6e-108">Return Value</span></span>  
 <span data-ttu-id="71b6e-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="71b6e-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71b6e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71b6e-110">Requirements</span></span>  
 <span data-ttu-id="71b6e-111">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="71b6e-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b6e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="71b6e-112">See also</span></span>

- [<span data-ttu-id="71b6e-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71b6e-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="71b6e-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71b6e-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="71b6e-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="71b6e-115">ALink API</span></span>](index.md)
