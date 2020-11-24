---
title: GetResolutionScope (Método)
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
ms.openlocfilehash: 6318890dd6f0259d8d6a7675380684a129c14c8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684685"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="e362c-102">GetResolutionScope (Método)</span><span class="sxs-lookup"><span data-stu-id="e362c-102">GetResolutionScope Method</span></span>

<span data-ttu-id="e362c-103">Recupera el ámbito de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="e362c-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e362c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e362c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e362c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e362c-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e362c-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e362c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e362c-107">Archivo que necesita una referencia.</span><span class="sxs-lookup"><span data-stu-id="e362c-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="e362c-108">Token de archivo en el que se define el tipo, normalmente recuperado con el [método importFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="e362c-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="e362c-109">Recibe la referencia del ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="e362c-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e362c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e362c-110">Return Value</span></span>  

 <span data-ttu-id="e362c-111">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e362c-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e362c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e362c-112">Requirements</span></span>  

 <span data-ttu-id="e362c-113">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="e362c-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e362c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e362c-114">See also</span></span>

- [<span data-ttu-id="e362c-115">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e362c-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e362c-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e362c-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e362c-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e362c-117">ALink API</span></span>](index.md)
