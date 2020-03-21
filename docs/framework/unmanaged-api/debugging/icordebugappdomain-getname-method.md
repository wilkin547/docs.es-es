---
title: ICorDebugAppDomain::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179086"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="e96db-102">ICorDebugAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="e96db-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="e96db-103">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e96db-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e96db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e96db-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e96db-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e96db-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="e96db-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="e96db-107">Establezca este valor en cero para poner este método en modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="e96db-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e96db-108">[fuera] Un puntero al tamaño del nombre o al `szName`número de caracteres devueltos realmente en .</span><span class="sxs-lookup"><span data-stu-id="e96db-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="e96db-109">En el modo de consulta, este valor permite al autor de la llamada saber qué tan grande debe asignar un búfer para el nombre.</span><span class="sxs-lookup"><span data-stu-id="e96db-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="e96db-110">[fuera] Matriz que almacena el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e96db-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e96db-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e96db-111">Remarks</span></span>  
 <span data-ttu-id="e96db-112">Un depurador `GetName` llama al método una vez para obtener el tamaño de un búfer necesario para el nombre.</span><span class="sxs-lookup"><span data-stu-id="e96db-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="e96db-113">El depurador asigna el búfer y, a continuación, llama al método una segunda vez para rellenar el búfer.</span><span class="sxs-lookup"><span data-stu-id="e96db-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="e96db-114">La primera llamada, para obtener el tamaño del nombre, se conoce como modo de *consulta*.</span><span class="sxs-lookup"><span data-stu-id="e96db-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e96db-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e96db-115">Requirements</span></span>  
 <span data-ttu-id="e96db-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e96db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96db-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e96db-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e96db-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e96db-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e96db-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e96db-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
