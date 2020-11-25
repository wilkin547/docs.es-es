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
ms.openlocfilehash: da32ce6a40378a6f88cf71bd7707be2079d71068
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717611"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="d0a2f-102">CompareAssemblyIdentity (Función)</span><span class="sxs-lookup"><span data-stu-id="d0a2f-102">CompareAssemblyIdentity Function</span></span>

<span data-ttu-id="d0a2f-103">Compara dos identidades de ensamblado para determinar si son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0a2f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d0a2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0a2f-105">Parameters</span></span>  

 `pwzAssemblyIdentity1`  
 <span data-ttu-id="d0a2f-106">de Identidad textual del primer ensamblado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="d0a2f-107">de Una marca booleana que indica la unificación especificada por el usuario para `pwzAssemblyIdentity1` .</span><span class="sxs-lookup"><span data-stu-id="d0a2f-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="d0a2f-108">de La identidad textual del segundo ensamblado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="d0a2f-109">de Una marca booleana que indica la unificación especificada por el usuario para `pwzAssemblyIdentity2` .</span><span class="sxs-lookup"><span data-stu-id="d0a2f-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="d0a2f-110">enuncia Una marca booleana que indica si los dos ensamblados son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="d0a2f-111">enuncia Una enumeración [assemblycomparisonresult (](assemblycomparisonresult-enumeration.md) que contiene información detallada acerca de la comparación.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0a2f-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0a2f-112">Return Value</span></span>  

 <span data-ttu-id="d0a2f-113">`pfEquivalent` Devuelve un valor booleano que indica si los dos ensamblados son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="d0a2f-114">`pResult` devuelve uno de los `AssemblyComparisonResult` valores de, para proporcionar un motivo más detallado para el valor de `pfEquivalent` .</span><span class="sxs-lookup"><span data-stu-id="d0a2f-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0a2f-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0a2f-115">Remarks</span></span>  

 <span data-ttu-id="d0a2f-116">`CompareAssemblyIdentity` comprueba si `pwzAssemblyIdentity1` y `pwzAssemblyIdentity2` son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="d0a2f-117">`pfEquivalent` está establecido en `true` una o varias de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d0a2f-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="d0a2f-118">Las dos identidades de ensamblado son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="d0a2f-119">En el caso de los ensamblados con nombre seguro, la equivalencia requiere que el nombre de ensamblado, la versión, el token de clave pública y la referencia cultural sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="d0a2f-120">En el caso de los ensamblados con nombre, la equivalencia requiere una coincidencia en el nombre y la referencia cultural del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="d0a2f-121">Ambas identidades de ensamblado hacen referencia a ensamblados que se ejecutan en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="d0a2f-122">Esta condición devuelve `true` aunque los números de versión de ensamblado no coincidan.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="d0a2f-123">Los dos ensamblados no son ensamblados administrados, pero `fUnified1` o `fUnified2` se estableció en `true` .</span><span class="sxs-lookup"><span data-stu-id="d0a2f-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="d0a2f-124">La `fUnified` marca indica que todos los números de versión hasta el número de versión del ensamblado con nombre seguro se consideran equivalentes al ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="d0a2f-125">Por ejemplo, si el valor de `pwzAssemblyIndentity1` es "myAssembly, version = 3.0.0.0, Culture = neutral, PublicKeyToken =...." y el valor de `fUnified1` es `true` , indica que todas las versiones de myAssembly de la versión 0.0.0.0 a 3.0.0.0 deben tratarse como equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="d0a2f-126">En tal caso, si `pwzAssemblyIndentity2` hace referencia al mismo ensamblado que `pwzAssemblyIndentity1` , salvo que tiene un número de versión inferior, `pfEquivalent` se establece en `true` .</span><span class="sxs-lookup"><span data-stu-id="d0a2f-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="d0a2f-127">Si `pwzAssemblyIdentity2` hace referencia a un número de versión superior, `pfEquivalent` se establece en `true` solo si el valor de `fUnified2` es `true` .</span><span class="sxs-lookup"><span data-stu-id="d0a2f-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="d0a2f-128">El `pResult` parámetro incluye información específica sobre por qué los dos ensamblados se consideran equivalentes o no equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d0a2f-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="d0a2f-129">Para obtener más información, vea [enumeración assemblycomparisonresult (](assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="d0a2f-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0a2f-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0a2f-130">Requirements</span></span>  

 <span data-ttu-id="d0a2f-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0a2f-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0a2f-132">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d0a2f-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d0a2f-133">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0a2f-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0a2f-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0a2f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a2f-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0a2f-135">See also</span></span>

- [<span data-ttu-id="d0a2f-136">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="d0a2f-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="d0a2f-137">AssemblyComparisonResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d0a2f-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
