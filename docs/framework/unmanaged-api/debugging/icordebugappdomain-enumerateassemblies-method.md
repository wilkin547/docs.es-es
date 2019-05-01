---
title: ICorDebugAppDomain::EnumerateAssemblies (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ce95daaee3c74ac57b107ab8bcb23d41e42cabb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989548"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="72fc5-102">ICorDebugAppDomain::EnumerateAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="72fc5-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="72fc5-103">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="72fc5-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72fc5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72fc5-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72fc5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72fc5-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="72fc5-106">[out] Un puntero a la dirección de un objeto ICorDebugAssemblyEnum que es el enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="72fc5-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72fc5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72fc5-107">Requirements</span></span>  
 <span data-ttu-id="72fc5-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72fc5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72fc5-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72fc5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72fc5-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72fc5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72fc5-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72fc5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
