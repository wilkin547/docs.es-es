---
title: AssemblyComparisonResult (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: cde25a9507006c89ef6490c13ae82033f04c2931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731038"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="52466-102">AssemblyComparisonResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="52466-102">AssemblyComparisonResult Enumeration</span></span>

<span data-ttu-id="52466-103">Indica la equivalencia de dos identidades de ensamblado, según lo determinado por la función [CompareAssemblyIdentity (](compareassemblyidentity-function.md) .</span><span class="sxs-lookup"><span data-stu-id="52466-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52466-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52466-104">Syntax</span></span>  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a><span data-ttu-id="52466-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="52466-105">Members</span></span>  
  
|<span data-ttu-id="52466-106">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="52466-106">Member name</span></span>|<span data-ttu-id="52466-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="52466-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="52466-108">Indica que todos los campos de ensamblado de la comparación coinciden.</span><span class="sxs-lookup"><span data-stu-id="52466-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="52466-109">Indica que los ensamblados se consideran equivalentes según la unificación de la versión de Common Language Runtime (CLR) de los números de versión de ensamblado en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="52466-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="52466-110">Indica una coincidencia parcial de los ensamblados en función de la unificación CLR de los números de versión de ensamblado en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="52466-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="52466-111">Indica una coincidencia parcial de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="52466-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="52466-112">Indica una coincidencia parcial de los ensamblados basándose en la unificación heredada de números de versión.</span><span class="sxs-lookup"><span data-stu-id="52466-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="52466-113">Indica una coincidencia parcial de ensamblados simplemente con nombre.</span><span class="sxs-lookup"><span data-stu-id="52466-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="52466-114">Indica que los ensamblados se consideran equivalentes en función de la unificación de CLR de los números de versión de las versiones heredadas del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52466-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="52466-115">Indica una coincidencia entre dos ensamblados simplemente con nombre cuyos números de versión se omitieron.</span><span class="sxs-lookup"><span data-stu-id="52466-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="52466-116">Indica que no se ha producido ninguna coincidencia entre los dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="52466-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="52466-117">Indica que los dos ensamblados coinciden, excepto en el caso de sus números de versión, que solo coinciden parcialmente.</span><span class="sxs-lookup"><span data-stu-id="52466-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="52466-118">Indica que los dos ensamblados coinciden, excepto los números de versión, que no coinciden.</span><span class="sxs-lookup"><span data-stu-id="52466-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="52466-119">Indica que no se conoce el motivo de la no equivalencia.</span><span class="sxs-lookup"><span data-stu-id="52466-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52466-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52466-120">Requirements</span></span>  

 <span data-ttu-id="52466-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52466-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52466-122">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="52466-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="52466-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52466-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52466-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52466-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52466-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52466-125">See also</span></span>

- [<span data-ttu-id="52466-126">CompareAssemblyIdentity (Función)</span><span class="sxs-lookup"><span data-stu-id="52466-126">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)
- [<span data-ttu-id="52466-127">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="52466-127">Fusion Enumerations</span></span>](fusion-enumerations.md)
