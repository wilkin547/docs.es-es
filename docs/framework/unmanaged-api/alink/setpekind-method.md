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
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680045"
---
# <a name="setpekind-method"></a><span data-ttu-id="90a61-102">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="90a61-102">SetPEKind Method</span></span>

<span data-ttu-id="90a61-103">Determina el tipo portable ejecutable, ya sea específico del equipo o independiente del equipo.</span><span class="sxs-lookup"><span data-stu-id="90a61-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90a61-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="90a61-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90a61-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="90a61-106">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="90a61-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="90a61-107">Token del archivo para el que se va a establecer el tipo de PE.</span><span class="sxs-lookup"><span data-stu-id="90a61-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="90a61-108">Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="90a61-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="90a61-109">Tipo de PE, como indica la [enumeración CorPEKind (](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="90a61-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="90a61-110">La arquitectura del equipo de destino, como se indica en el encabezado NT.</span><span class="sxs-lookup"><span data-stu-id="90a61-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90a61-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="90a61-111">Return Value</span></span>  

 <span data-ttu-id="90a61-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="90a61-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a61-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90a61-113">Requirements</span></span>  

 <span data-ttu-id="90a61-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="90a61-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a61-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90a61-115">See also</span></span>

- [<span data-ttu-id="90a61-116">Método GetPEKind</span><span class="sxs-lookup"><span data-stu-id="90a61-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="90a61-117">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90a61-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="90a61-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90a61-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="90a61-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="90a61-119">ALink API</span></span>](index.md)
