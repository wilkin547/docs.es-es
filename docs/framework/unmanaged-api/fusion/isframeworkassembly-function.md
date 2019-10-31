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
ms.openlocfilehash: e30b6f2d2254d2d107c4c82a2c5664850ce6ec23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123067"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="ab26a-102">IsFrameworkAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="ab26a-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="ab26a-103">Obtiene un valor que indica si el ensamblado especificado está administrado.</span><span class="sxs-lookup"><span data-stu-id="ab26a-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab26a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab26a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab26a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab26a-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="ab26a-106">de Nombre del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="ab26a-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="ab26a-107">enuncia Valor booleano que indica si el ensamblado está administrado.</span><span class="sxs-lookup"><span data-stu-id="ab26a-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="ab26a-108">de Una cadena no canónica que contiene la identidad única del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab26a-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="ab26a-109">[in] Tamaño de `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ab26a-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab26a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab26a-110">Remarks</span></span>  
 <span data-ttu-id="ab26a-111">El parámetro `pwzAssemblyReference` es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab26a-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="ab26a-112">Si este ensamblado forma parte del .NET Framework, el parámetro `pbIsFrameworkAssembly` contendrá un valor booleano de `true`.</span><span class="sxs-lookup"><span data-stu-id="ab26a-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="ab26a-113">Si el ensamblado con nombre no forma parte de la .NET Framework, o si el parámetro `pwzAssemblyReference` no tiene un nombre de ensamblado, `pbIsFrameworkAssembly` contendrá un valor booleano de `false`.</span><span class="sxs-lookup"><span data-stu-id="ab26a-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab26a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab26a-114">Requirements</span></span>  
 <span data-ttu-id="ab26a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab26a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab26a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab26a-116">See also</span></span>

- [<span data-ttu-id="ab26a-117">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="ab26a-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
