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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e351c61f7e8bfc254a6fc8ea12c8a94fc393e3fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478159"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="a5447-102">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="a5447-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="a5447-103">Recupera atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5447-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5447-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5447-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5447-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5447-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a5447-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="a5447-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="a5447-107">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="a5447-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="a5447-108">Use `mdTokenNill` para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="a5447-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="a5447-109">Recibe los tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a5447-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a5447-110">Especifica el tamaño de `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="a5447-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="a5447-111">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="a5447-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5447-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5447-112">Return Value</span></span>  
 <span data-ttu-id="a5447-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a5447-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5447-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5447-114">Requirements</span></span>  
 <span data-ttu-id="a5447-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="a5447-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5447-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5447-116">See also</span></span>
- [<span data-ttu-id="a5447-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5447-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a5447-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5447-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a5447-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a5447-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
