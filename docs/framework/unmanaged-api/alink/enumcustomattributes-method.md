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
ms.openlocfilehash: 5a3d7d3bb05a878f4d9832cf39a8e8863929c4e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403219"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="f89ef-102">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="f89ef-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="f89ef-103">Recupera atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f89ef-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f89ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f89ef-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f89ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f89ef-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="f89ef-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="f89ef-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="f89ef-107">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="f89ef-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="f89ef-108">Use `mdTokenNill` para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="f89ef-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="f89ef-109">Recibe los tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f89ef-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f89ef-110">Especifica el tamaño de `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="f89ef-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="f89ef-111">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="f89ef-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f89ef-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f89ef-112">Return Value</span></span>  
 <span data-ttu-id="f89ef-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="f89ef-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f89ef-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f89ef-114">Requirements</span></span>  
 <span data-ttu-id="f89ef-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="f89ef-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89ef-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f89ef-116">See Also</span></span>  
 [<span data-ttu-id="f89ef-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f89ef-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f89ef-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f89ef-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f89ef-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f89ef-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
