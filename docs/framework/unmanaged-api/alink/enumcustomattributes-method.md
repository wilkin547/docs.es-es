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
ms.openlocfilehash: 5d8827f46a12bd090fa27e71072d833607d34677
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777349"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="60dcf-102">EnumCustomAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="60dcf-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="60dcf-103">Recupera los atributos personalizados de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="60dcf-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60dcf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60dcf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="60dcf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60dcf-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="60dcf-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="60dcf-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="60dcf-107">Tipo de atributos que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="60dcf-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="60dcf-108">Se `mdTokenNill` utiliza para todos los atributos.</span><span class="sxs-lookup"><span data-stu-id="60dcf-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="60dcf-109">Recibe tokens de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="60dcf-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="60dcf-110">Especifica el tamaño `rCustomValues` de la matriz.</span><span class="sxs-lookup"><span data-stu-id="60dcf-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="60dcf-111">Opcionalmente, recibe el recuento de valores de token.</span><span class="sxs-lookup"><span data-stu-id="60dcf-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60dcf-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="60dcf-112">Return Value</span></span>  
 <span data-ttu-id="60dcf-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="60dcf-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60dcf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60dcf-114">Requirements</span></span>  
 <span data-ttu-id="60dcf-115">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="60dcf-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60dcf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="60dcf-116">See also</span></span>

- [<span data-ttu-id="60dcf-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60dcf-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="60dcf-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="60dcf-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="60dcf-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="60dcf-119">ALink API</span></span>](index.md)
