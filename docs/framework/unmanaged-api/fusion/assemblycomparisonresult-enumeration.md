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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03b8ecc996e14263510e2d0a658cec020696c263
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914506"
---
# <a name="assemblycomparisonresult-enumeration"></a><span data-ttu-id="918fc-102">AssemblyComparisonResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="918fc-102">AssemblyComparisonResult Enumeration</span></span>
<span data-ttu-id="918fc-103">Indica la equivalencia de dos identidades de ensamblado, según lo determinado por la [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="918fc-103">Indicates the equivalence of two assembly identities, as determined by the [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="918fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="918fc-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="918fc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="918fc-105">Members</span></span>  
  
|<span data-ttu-id="918fc-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="918fc-106">Member name</span></span>|<span data-ttu-id="918fc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="918fc-107">Description</span></span>|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|<span data-ttu-id="918fc-108">Indica que el ensamblado de todos los campos en la coincidencia de comparación.</span><span class="sxs-lookup"><span data-stu-id="918fc-108">Indicates that all assembly fields in the comparison match.</span></span>|  
|`ACR_EquivalentFXUnified`|<span data-ttu-id="918fc-109">Indica que los ensamblados se consideran equivalentes basándose en la unificación de versión (CLR) en tiempo de ejecución de lenguaje común de los números de versión de ensamblado en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="918fc-109">Indicates that assemblies are considered equivalent based on the common language runtime version (CLR) unification of assembly version numbers in the .NET Framework version 2.0.</span></span>|  
|`ACR_EquivalentPartialFXUnified`|<span data-ttu-id="918fc-110">Indica a una coincidencia parcial de los ensamblados en función de la unificación de CLR de números de versión de ensamblado de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="918fc-110">Indicates a partial match of the assemblies based on the CLR unification of assembly version numbers in the .NET Framework 2.0.</span></span>|  
|`ACR_EquivalentPartialMatch`|<span data-ttu-id="918fc-111">Indica a una coincidencia parcial de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="918fc-111">Indicates a partial match of the assemblies.</span></span>|  
|`ACR_EquivalentPartialUnified`|<span data-ttu-id="918fc-112">Indica a una coincidencia parcial de los ensamblados basada en la unificación heredada de números de versión.</span><span class="sxs-lookup"><span data-stu-id="918fc-112">Indicates a partial match of the assemblies based on legacy unification of version numbers.</span></span>|  
|`ACR_EquivalentPartialWeakNamed`|<span data-ttu-id="918fc-113">Indica a una coincidencia parcial de ensamblados con nombres simples.</span><span class="sxs-lookup"><span data-stu-id="918fc-113">Indicates a partial match of simply named assemblies.</span></span>|  
|`ACR_EquivalentUnified`|<span data-ttu-id="918fc-114">Indica que los ensamblados se consideran equivalentes basándose en la unificación de CLR de los números de versión de las versiones heredadas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="918fc-114">Indicates that assemblies are considered equivalent based on the CLR unification of version numbers in legacy versions of the .NET Framework.</span></span>|  
|`ACR_EquivalentWeakNamed`|<span data-ttu-id="918fc-115">Indica a una coincidencia entre dos ensamblados con nombres simples cuyos números de versión se han omitido.</span><span class="sxs-lookup"><span data-stu-id="918fc-115">Indicates a match between two simply named assemblies whose version numbers were ignored.</span></span>|  
|`ACR_NonEquivalent`|<span data-ttu-id="918fc-116">Indica que se produjo ninguna coincidencia entre los dos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="918fc-116">Indicates that no match occurred between the two assemblies.</span></span>|  
|`ACR_NonEquivalentPartialVersion`|<span data-ttu-id="918fc-117">Indica que los dos ensamblados coinciden, aunque sus números de versión sólo coinciden parcialmente.</span><span class="sxs-lookup"><span data-stu-id="918fc-117">Indicates that the two assemblies match except for their version numbers, which match only partially.</span></span>|  
|`ACR_NonEquivalentVersion`|<span data-ttu-id="918fc-118">Indica que los dos ensamblados coinciden, aunque sus números de versión que no coinciden.</span><span class="sxs-lookup"><span data-stu-id="918fc-118">Indicates that the two assemblies match except for their version numbers, which do not match.</span></span>|  
|`ACR_Unknown`|<span data-ttu-id="918fc-119">Indica que se desconoce la razón de no equivalencia.</span><span class="sxs-lookup"><span data-stu-id="918fc-119">Indicates that the reason for non-equivalency is not known.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="918fc-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="918fc-120">Requirements</span></span>  
 <span data-ttu-id="918fc-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="918fc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="918fc-122">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="918fc-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="918fc-123">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="918fc-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="918fc-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="918fc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918fc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="918fc-125">See also</span></span>

- [<span data-ttu-id="918fc-126">CompareAssemblyIdentity (Función)</span><span class="sxs-lookup"><span data-stu-id="918fc-126">CompareAssemblyIdentity Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [<span data-ttu-id="918fc-127">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="918fc-127">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
