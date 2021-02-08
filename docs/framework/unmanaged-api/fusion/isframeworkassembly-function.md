---
description: 'Más información acerca de: Isframeworkassembly ((función)'
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
ms.openlocfilehash: 8f264df7b1ae5c494298b11ebd94cc93aed5543a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800024"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="0f35a-103">IsFrameworkAssembly (Función)</span><span class="sxs-lookup"><span data-stu-id="0f35a-103">IsFrameworkAssembly Function</span></span>

<span data-ttu-id="0f35a-104">Obtiene un valor que indica si el ensamblado especificado está administrado.</span><span class="sxs-lookup"><span data-stu-id="0f35a-104">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f35a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f35a-105">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f35a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f35a-106">Parameters</span></span>  

 `pwzAssemblyReference`  
 <span data-ttu-id="0f35a-107">de Nombre del ensamblado que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="0f35a-107">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="0f35a-108">enuncia Valor booleano que indica si el ensamblado está administrado.</span><span class="sxs-lookup"><span data-stu-id="0f35a-108">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="0f35a-109">de Una cadena no canónica que contiene la identidad única del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0f35a-109">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="0f35a-110">[in] Tamaño de `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="0f35a-110">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f35a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f35a-111">Remarks</span></span>  

 <span data-ttu-id="0f35a-112">El `pwzAssemblyReference` parámetro es un puntero a una cadena de caracteres que contiene el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0f35a-112">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="0f35a-113">Si este ensamblado forma parte del .NET Framework, el `pbIsFrameworkAssembly` parámetro contendrá un valor booleano de `true` .</span><span class="sxs-lookup"><span data-stu-id="0f35a-113">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="0f35a-114">Si el ensamblado con nombre no forma parte de la .NET Framework, o si el parámetro no es `pwzAssemblyReference` un ensamblado, contendrá `pbIsFrameworkAssembly` un valor booleano de `false` .</span><span class="sxs-lookup"><span data-stu-id="0f35a-114">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f35a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f35a-115">Requirements</span></span>  

 <span data-ttu-id="0f35a-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f35a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f35a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f35a-117">See also</span></span>

- [<span data-ttu-id="0f35a-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="0f35a-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
