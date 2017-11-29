---
title: "ICorDebugAppDomain::GetName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590bfb5d7d8cac8e322bddfe6258ad9bf377dad6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="5e1ea-102">ICorDebugAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="5e1ea-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="5e1ea-103">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e1ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e1ea-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e1ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e1ea-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5e1ea-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="5e1ea-107">Establezca este valor en cero para poner este método en modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5e1ea-108">[out] Un puntero al tamaño del nombre o el número de caracteres devueltos realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="5e1ea-109">En el modo de consulta, este valor permite al llamador saber el tamaño del búfer para asignar el nombre.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="5e1ea-110">[out] Una matriz que almacena el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e1ea-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e1ea-111">Remarks</span></span>  
 <span data-ttu-id="5e1ea-112">Llama a un depurador el `GetName` una vez al método para obtener el tamaño de un búfer necesario para el nombre.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="5e1ea-113">El depurador asigna el búfer y, a continuación, llama al método una segunda vez para llenar el búfer.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="5e1ea-114">La primera llamada, para obtener el tamaño del nombre, se conoce como *el modo de consulta*.</span><span class="sxs-lookup"><span data-stu-id="5e1ea-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e1ea-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e1ea-115">Requirements</span></span>  
 <span data-ttu-id="5e1ea-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e1ea-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e1ea-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e1ea-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e1ea-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e1ea-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e1ea-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e1ea-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
