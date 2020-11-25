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
ms.openlocfilehash: 4e8aeef3520c4d5c9735b2c8975ac1e39470ba93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717028"
---
# <a name="closeassembly-method"></a><span data-ttu-id="e4126-102">CloseAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="e4126-102">CloseAssembly Method</span></span>

<span data-ttu-id="e4126-103">Finaliza las operaciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4126-103">Finalizes assembly operations.</span></span> <span data-ttu-id="e4126-104">Llame a este método antes de iniciar un nuevo ensamblado o módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="e4126-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4126-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4126-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4126-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4126-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e4126-107">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4126-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4126-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4126-108">Return Value</span></span>  

 <span data-ttu-id="e4126-109">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4126-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4126-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4126-110">Requirements</span></span>  

 <span data-ttu-id="e4126-111">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="e4126-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4126-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4126-112">See also</span></span>

- [<span data-ttu-id="e4126-113">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4126-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e4126-114">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4126-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e4126-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e4126-115">ALink API</span></span>](index.md)
