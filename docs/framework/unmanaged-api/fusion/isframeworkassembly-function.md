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
ms.openlocfilehash: c3fd130759ab11b54b597d5c099c33dab93070ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429255"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="d0f31-102">IsFrameworkAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="d0f31-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="d0f31-103">Obtiene un valor que indica si el ensamblado especificado es administrado.</span><span class="sxs-lookup"><span data-stu-id="d0f31-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0f31-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0f31-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0f31-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="d0f31-106">[in] El nombre del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="d0f31-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="d0f31-107">[out] Un valor booleano que indica si el ensamblado administrado.</span><span class="sxs-lookup"><span data-stu-id="d0f31-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="d0f31-108">[in] Una cadena sin formato canónico que contiene la identidad única del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0f31-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="d0f31-109">[in] Tamaño de `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d0f31-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0f31-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0f31-110">Remarks</span></span>  
 <span data-ttu-id="d0f31-111">El `pwzAssemblyReference` parámetro es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d0f31-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="d0f31-112">Si este ensamblado forma parte de .NET Framework, el `pbIsFrameworkAssembly` parámetro contendrá un valor booleano de `true`.</span><span class="sxs-lookup"><span data-stu-id="d0f31-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="d0f31-113">Si el ensamblado con nombre no forma parte de .NET Framework, o si la `pwzAssemblyReference` parámetro no incluye el nombre de un ensamblado, `pbIsFrameworkAssembly` contendrá un valor booleano de `false`.</span><span class="sxs-lookup"><span data-stu-id="d0f31-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0f31-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0f31-114">Requirements</span></span>  
 <span data-ttu-id="d0f31-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0f31-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f31-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0f31-116">See Also</span></span>  
 [<span data-ttu-id="d0f31-117">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="d0f31-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
