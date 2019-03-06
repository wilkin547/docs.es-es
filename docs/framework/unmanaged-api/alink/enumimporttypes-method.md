---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355745"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="f0fcd-102">EnumImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="f0fcd-102">EnumImportTypes Method</span></span>

<span data-ttu-id="f0fcd-103">Enumera cada tipo en cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="f0fcd-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0fcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0fcd-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="f0fcd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0fcd-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="f0fcd-106">Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="f0fcd-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="f0fcd-107">Número máximo de tipos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="f0fcd-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="f0fcd-108">Recibe los tokens de tipo, no debe superar los `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="f0fcd-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="f0fcd-109">Recibe el número real de tipo en `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="f0fcd-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f0fcd-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f0fcd-110">Return Value</span></span>

<span data-ttu-id="f0fcd-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="f0fcd-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0fcd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0fcd-112">Requirements</span></span>

<span data-ttu-id="f0fcd-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="f0fcd-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="f0fcd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0fcd-114">See also</span></span>

- [<span data-ttu-id="f0fcd-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0fcd-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f0fcd-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0fcd-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f0fcd-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f0fcd-117">ALink API</span></span>](index.md)