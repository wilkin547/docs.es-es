---
title: CompareAssemblyIdentity (Función)
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108922"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="01319-102">CompareAssemblyIdentity (Función)</span><span class="sxs-lookup"><span data-stu-id="01319-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="01319-103">Compara dos identidades de ensamblado para determinar si son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01319-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01319-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01319-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="01319-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01319-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="01319-106">de Identidad textual del primer ensamblado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="01319-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="01319-107">de Una marca booleana que indica la unificación especificada por el usuario para `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="01319-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="01319-108">de La identidad textual del segundo ensamblado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="01319-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="01319-109">de Una marca booleana que indica la unificación especificada por el usuario para `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="01319-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="01319-110">enuncia Una marca booleana que indica si los dos ensamblados son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01319-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="01319-111">enuncia Una enumeración [assemblycomparisonresult (](assemblycomparisonresult-enumeration.md) que contiene información detallada acerca de la comparación.</span><span class="sxs-lookup"><span data-stu-id="01319-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01319-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="01319-112">Return Value</span></span>  
 <span data-ttu-id="01319-113">`pfEquivalent` devuelve un valor booleano que indica si los dos ensamblados son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01319-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="01319-114">`pResult` devuelve uno de los valores de `AssemblyComparisonResult`, para proporcionar una razón más detallada para el valor de `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="01319-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01319-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01319-115">Remarks</span></span>  
 <span data-ttu-id="01319-116">`CompareAssemblyIdentity` comprueba si `pwzAssemblyIdentity1` y `pwzAssemblyIdentity2` son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01319-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="01319-117">`pfEquivalent` se establece en `true` en una o varias de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="01319-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="01319-118">Las dos identidades de ensamblado son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01319-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="01319-119">En el caso de los ensamblados con nombre seguro, la equivalencia requiere que el nombre de ensamblado, la versión, el token de clave pública y la referencia cultural sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="01319-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="01319-120">En el caso de los ensamblados con nombre, la equivalencia requiere una coincidencia en el nombre y la referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="01319-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="01319-121">Ambas identidades de ensamblado hacen referencia a ensamblados que se ejecutan en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01319-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="01319-122">Esta condición devuelve `true` incluso si los números de versión de ensamblado no coinciden.</span><span class="sxs-lookup"><span data-stu-id="01319-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="01319-123">Los dos ensamblados no son ensamblados administrados, pero `fUnified1` o `fUnified2` se estableció en `true`.</span><span class="sxs-lookup"><span data-stu-id="01319-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="01319-124">La marca `fUnified` indica que todos los números de versión hasta el número de versión del ensamblado con nombre seguro se consideran equivalentes al ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="01319-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="01319-125">Por ejemplo, si el valor de `pwzAssemblyIndentity1` es "myAssembly, version = 3.0.0.0, Culture = neutral, publicKeyToken =...." y el valor de `fUnified1` es `true`, esto indica que todas las versiones de myAssembly de la versión 0.0.0.0 a 3.0.0.0 deben tratarse como Equivalent.</span><span class="sxs-lookup"><span data-stu-id="01319-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="01319-126">En tal caso, si `pwzAssemblyIndentity2` hace referencia al mismo ensamblado que `pwzAssemblyIndentity1`, salvo que tiene un número de versión inferior, `pfEquivalent` se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="01319-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="01319-127">Si `pwzAssemblyIdentity2` hace referencia a un número de versión superior, `pfEquivalent` se establece en `true` solo si el valor de `fUnified2` es `true`.</span><span class="sxs-lookup"><span data-stu-id="01319-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="01319-128">El parámetro `pResult` incluye información específica sobre por qué los dos ensamblados se consideran equivalentes o no equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01319-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="01319-129">Para obtener más información, vea [enumeración assemblycomparisonresult (](assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="01319-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01319-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01319-130">Requirements</span></span>  
 <span data-ttu-id="01319-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01319-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01319-132">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="01319-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="01319-133">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01319-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01319-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01319-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01319-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="01319-135">See also</span></span>

- [<span data-ttu-id="01319-136">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="01319-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="01319-137">AssemblyComparisonResult (enumeración)</span><span class="sxs-lookup"><span data-stu-id="01319-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
