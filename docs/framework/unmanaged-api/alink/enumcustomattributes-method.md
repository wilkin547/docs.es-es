---
description: 'Más información sobre: método Enumcustomattributes ('
title: EnumCustomAttributes (Método)
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
ms.openlocfilehash: d5b537462745914903f0cdb1e9f4436f2c27a68d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638142"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="db9e6-103">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="db9e6-103">EnumCustomAttributes Method</span></span>

<span data-ttu-id="db9e6-104">Recupera los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db9e6-104">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db9e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db9e6-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="db9e6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db9e6-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="db9e6-107">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="db9e6-107">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="db9e6-108">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="db9e6-108">Type of attributes to be enumerated.</span></span> <span data-ttu-id="db9e6-109">Se utiliza `mdTokenNill` para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="db9e6-109">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="db9e6-110">Recibe tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="db9e6-110">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="db9e6-111">Especifica el tamaño de la `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="db9e6-111">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="db9e6-112">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="db9e6-112">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db9e6-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db9e6-113">Return Value</span></span>  

 <span data-ttu-id="db9e6-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="db9e6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db9e6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db9e6-115">Requirements</span></span>  

 <span data-ttu-id="db9e6-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="db9e6-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db9e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="db9e6-117">See also</span></span>

- [<span data-ttu-id="db9e6-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db9e6-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="db9e6-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db9e6-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="db9e6-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="db9e6-120">ALink API</span></span>](index.md)
