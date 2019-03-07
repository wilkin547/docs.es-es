---
title: IsFrameworkAssembly (Función)
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0fb4c98ff2c8b071f05b42aefed61485001e97f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480330"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="e91dd-102">IsFrameworkAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="e91dd-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="e91dd-103">Obtiene un valor que indica si el ensamblado especificado está administrado.</span><span class="sxs-lookup"><span data-stu-id="e91dd-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e91dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e91dd-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e91dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e91dd-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="e91dd-106">[in] El nombre del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="e91dd-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="e91dd-107">[out] Un valor booleano que indica si el ensamblado es administrado.</span><span class="sxs-lookup"><span data-stu-id="e91dd-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="e91dd-108">[in] Una cadena sin formato canónico que contiene la identidad única del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e91dd-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="e91dd-109">[in] Tamaño de `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="e91dd-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e91dd-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e91dd-110">Remarks</span></span>  
 <span data-ttu-id="e91dd-111">El `pwzAssemblyReference` parámetro es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e91dd-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="e91dd-112">Si este ensamblado forma parte de .NET Framework, el `pbIsFrameworkAssembly` parámetro contendrá un valor booleano de `true`.</span><span class="sxs-lookup"><span data-stu-id="e91dd-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="e91dd-113">Si el ensamblado con nombre no forma parte de .NET Framework, o si el `pwzAssemblyReference` parámetro no es un ensamblado, el nombre `pbIsFrameworkAssembly` contendrá un valor booleano de `false`.</span><span class="sxs-lookup"><span data-stu-id="e91dd-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e91dd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e91dd-114">Requirements</span></span>  
 <span data-ttu-id="e91dd-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e91dd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e91dd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e91dd-116">See also</span></span>
- [<span data-ttu-id="e91dd-117">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="e91dd-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
