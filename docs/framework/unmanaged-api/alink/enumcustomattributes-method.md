---
title: "EnumCustomAttributes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location: alink.dll
api_type: COM
f1_keywords: EnumCustomAttributes
helpviewer_keywords: EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: febaba5155753e9d60a3708582f4f58bd7861ec7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="5d2a7-102">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="5d2a7-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="5d2a7-103">Recupera atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d2a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d2a7-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d2a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d2a7-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="5d2a7-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="5d2a7-107">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="5d2a7-108">Use `mdTokenNill` para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="5d2a7-109">Recibe los tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5d2a7-110">Especifica el tamaño de `rCustomValues` matriz.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="5d2a7-111">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d2a7-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d2a7-112">Return Value</span></span>  
 <span data-ttu-id="5d2a7-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="5d2a7-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d2a7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d2a7-114">Requirements</span></span>  
 <span data-ttu-id="5d2a7-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="5d2a7-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d2a7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d2a7-116">See Also</span></span>  
 [<span data-ttu-id="5d2a7-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d2a7-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5d2a7-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d2a7-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5d2a7-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="5d2a7-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
