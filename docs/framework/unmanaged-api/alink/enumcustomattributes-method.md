---
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
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684855"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="ef4c6-102">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="ef4c6-102">EnumCustomAttributes Method</span></span>

<span data-ttu-id="ef4c6-103">Recupera los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef4c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef4c6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef4c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef4c6-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="ef4c6-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ef4c6-107">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="ef4c6-108">Se utiliza `mdTokenNill` para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="ef4c6-109">Recibe tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ef4c6-110">Especifica el tamaño de la `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="ef4c6-111">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef4c6-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef4c6-112">Return Value</span></span>  

 <span data-ttu-id="ef4c6-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="ef4c6-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef4c6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef4c6-114">Requirements</span></span>  

 <span data-ttu-id="ef4c6-115">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="ef4c6-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4c6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef4c6-116">See also</span></span>

- [<span data-ttu-id="ef4c6-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef4c6-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ef4c6-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef4c6-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ef4c6-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ef4c6-119">ALink API</span></span>](index.md)
