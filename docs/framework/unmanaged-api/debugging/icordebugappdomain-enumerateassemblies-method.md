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
ms.openlocfilehash: 13137dcf7c2edd96397916cc7db905c9e48a3d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401605"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="8501f-102">ICorDebugAppDomain::EnumerateAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="8501f-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="8501f-103">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8501f-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8501f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8501f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8501f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8501f-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="8501f-106">[out] Un puntero a la dirección de un objeto ICorDebugAssemblyEnum que es el enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8501f-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8501f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8501f-107">Requirements</span></span>  
 <span data-ttu-id="8501f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8501f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8501f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8501f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8501f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8501f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8501f-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8501f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
