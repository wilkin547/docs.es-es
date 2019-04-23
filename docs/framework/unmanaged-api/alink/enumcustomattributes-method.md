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
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199146"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="90050-102">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="90050-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="90050-103">Recupera atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90050-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90050-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90050-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="90050-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90050-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="90050-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="90050-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="90050-107">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="90050-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="90050-108">Use `mdTokenNill` para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="90050-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="90050-109">Recibe los tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="90050-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="90050-110">Especifica el tamaño de `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="90050-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="90050-111">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="90050-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90050-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90050-112">Return Value</span></span>  
 <span data-ttu-id="90050-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="90050-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90050-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90050-114">Requirements</span></span>  
 <span data-ttu-id="90050-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="90050-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90050-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="90050-116">See also</span></span>

- [<span data-ttu-id="90050-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="90050-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="90050-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="90050-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="90050-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="90050-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
