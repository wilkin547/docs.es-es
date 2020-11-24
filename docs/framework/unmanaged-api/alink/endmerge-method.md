---
title: EndMerge (Método)
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
ms.openlocfilehash: ed4ac7b12caa0dd78b79554258de62b8752553e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684933"
---
# <a name="endmerge-method"></a><span data-ttu-id="b03e2-102">EndMerge (Método)</span><span class="sxs-lookup"><span data-stu-id="b03e2-102">EndMerge Method</span></span>

<span data-ttu-id="b03e2-103">Indica que todos los atributos personalizados se han combinado en el ámbito de emisión.</span><span class="sxs-lookup"><span data-stu-id="b03e2-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b03e2-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b03e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b03e2-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="b03e2-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b03e2-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b03e2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b03e2-107">Return Value</span></span>  

 <span data-ttu-id="b03e2-108">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="b03e2-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03e2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b03e2-109">Requirements</span></span>  

 <span data-ttu-id="b03e2-110">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="b03e2-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03e2-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b03e2-111">See also</span></span>

- [<span data-ttu-id="b03e2-112">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b03e2-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b03e2-113">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b03e2-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b03e2-114">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b03e2-114">ALink API</span></span>](index.md)
