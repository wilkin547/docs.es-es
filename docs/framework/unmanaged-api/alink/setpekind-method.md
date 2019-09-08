---
title: SetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a48dbd38d357b668c2794ae6305ceb9cad3dcf4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787194"
---
# <a name="setpekind-method"></a><span data-ttu-id="15191-102">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="15191-102">SetPEKind Method</span></span>
<span data-ttu-id="15191-103">Determina el tipo portable ejecutable, ya sea específico del equipo o independiente del equipo.</span><span class="sxs-lookup"><span data-stu-id="15191-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15191-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15191-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="15191-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15191-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="15191-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="15191-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="15191-107">Token del archivo para el que se va a establecer el tipo de PE.</span><span class="sxs-lookup"><span data-stu-id="15191-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="15191-108">Puede ser null si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="15191-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="15191-109">Tipo de PE, como indica la [enumeración CorPEKind (](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="15191-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="15191-110">La arquitectura del equipo de destino, como se indica en el encabezado NT.</span><span class="sxs-lookup"><span data-stu-id="15191-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15191-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15191-111">Return Value</span></span>  
 <span data-ttu-id="15191-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="15191-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15191-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15191-113">Requirements</span></span>  
 <span data-ttu-id="15191-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="15191-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15191-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="15191-115">See also</span></span>

- [<span data-ttu-id="15191-116">GetPEKind (método)</span><span class="sxs-lookup"><span data-stu-id="15191-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="15191-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15191-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="15191-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15191-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="15191-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="15191-119">ALink API</span></span>](index.md)
