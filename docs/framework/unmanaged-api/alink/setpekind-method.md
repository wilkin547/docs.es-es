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
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179389"
---
# <a name="setpekind-method"></a><span data-ttu-id="2d8f6-102">SetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="2d8f6-102">SetPEKind Method</span></span>
<span data-ttu-id="2d8f6-103">Determina el tipo ejecutable portátil, específico de la máquina o independiente de la máquina.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d8f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d8f6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="2d8f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d8f6-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2d8f6-106">ID del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2d8f6-107">Token de archivo para el que se va a establecer el tipo PE.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="2d8f6-108">Puede ser `AssemblyID` NULL si no indica un netmodule sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="2d8f6-109">El tipo de PE, como se indica en [corPEKind (enumeración).](../metadata/corpekind-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="2d8f6-109">The type of PE, as indicated by the [CorPEKind Enumeration](../metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="2d8f6-110">La arquitectura de la máquina de destino, como se indica en el encabezado NT.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d8f6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d8f6-111">Return Value</span></span>  
 <span data-ttu-id="2d8f6-112">Devuelve S_OK si el método se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d8f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d8f6-113">Requirements</span></span>  
 <span data-ttu-id="2d8f6-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="2d8f6-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d8f6-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d8f6-115">See also</span></span>

- [<span data-ttu-id="2d8f6-116">GetPEKind (Método)</span><span class="sxs-lookup"><span data-stu-id="2d8f6-116">GetPEKind Method</span></span>](../metadata/imetadataimport2-getpekind-method.md)
- [<span data-ttu-id="2d8f6-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d8f6-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2d8f6-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d8f6-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2d8f6-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="2d8f6-119">ALink API</span></span>](index.md)
