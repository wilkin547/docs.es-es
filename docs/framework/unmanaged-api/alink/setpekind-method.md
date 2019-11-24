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
ms.openlocfilehash: dfbc10bdbe633450dee2e27524c29ead21fb739e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445536"
---
# <a name="setpekind-method"></a><span data-ttu-id="ec25e-102">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="ec25e-102">SetPEKind Method</span></span>
<span data-ttu-id="ec25e-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span><span class="sxs-lookup"><span data-stu-id="ec25e-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec25e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec25e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="ec25e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec25e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ec25e-106">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="ec25e-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ec25e-107">Token of file for which the PE type is to be set.</span><span class="sxs-lookup"><span data-stu-id="ec25e-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="ec25e-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span><span class="sxs-lookup"><span data-stu-id="ec25e-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="ec25e-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ec25e-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="ec25e-110">The target machine architecture, as indicated in the NT header.</span><span class="sxs-lookup"><span data-stu-id="ec25e-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec25e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec25e-111">Return Value</span></span>  
 <span data-ttu-id="ec25e-112">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="ec25e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec25e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec25e-113">Requirements</span></span>  
 <span data-ttu-id="ec25e-114">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="ec25e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec25e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec25e-115">See also</span></span>

- [<span data-ttu-id="ec25e-116">GetPEKind (método)</span><span class="sxs-lookup"><span data-stu-id="ec25e-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="ec25e-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec25e-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ec25e-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec25e-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ec25e-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ec25e-119">ALink API</span></span>](index.md)
