---
description: 'Más información sobre: método Enumimporttypes ('
title: EnumImportTypes (Método)
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: 39570740f3560f5bfef8ba80b95c0eb2aca41f59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638124"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="65d6b-103">EnumImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="65d6b-103">EnumImportTypes Method</span></span>

<span data-ttu-id="65d6b-104">Enumera cada tipo de cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="65d6b-104">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="65d6b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65d6b-105">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="65d6b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65d6b-106">Parameters</span></span>

`hEnum`\
<span data-ttu-id="65d6b-107">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="65d6b-107">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="65d6b-108">Número máximo de tipos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="65d6b-108">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="65d6b-109">Recibe tokens de tipo, no superar `dwMax` .</span><span class="sxs-lookup"><span data-stu-id="65d6b-109">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="65d6b-110">Recibe el número real de tipo en `aTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="65d6b-110">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="65d6b-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65d6b-111">Return Value</span></span>

<span data-ttu-id="65d6b-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="65d6b-112">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="65d6b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65d6b-113">Requirements</span></span>

<span data-ttu-id="65d6b-114">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="65d6b-114">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="65d6b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="65d6b-115">See also</span></span>

- [<span data-ttu-id="65d6b-116">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65d6b-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="65d6b-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65d6b-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="65d6b-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="65d6b-118">ALink API</span></span>](index.md)
