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
ms.openlocfilehash: 2c9aa6792885c685195049948a540453b1f5235e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110310"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="ccc25-102">ICorDebugAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="ccc25-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="ccc25-103">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccc25-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccc25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccc25-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccc25-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ccc25-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="ccc25-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="ccc25-107">Establezca este valor en cero para poner este método en modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="ccc25-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ccc25-108">enuncia Puntero al tamaño del nombre o número de caracteres devueltos realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="ccc25-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="ccc25-109">En el modo de consulta, este valor permite que el autor de la llamada sepa el tamaño de un búfer que se va a asignar al nombre.</span><span class="sxs-lookup"><span data-stu-id="ccc25-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="ccc25-110">enuncia Matriz que almacena el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ccc25-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccc25-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccc25-111">Remarks</span></span>  
 <span data-ttu-id="ccc25-112">Un depurador llama una vez al método `GetName` para obtener el tamaño de un búfer necesario para el nombre.</span><span class="sxs-lookup"><span data-stu-id="ccc25-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="ccc25-113">El depurador asigna el búfer y, a continuación, llama al método una segunda vez para rellenar el búfer.</span><span class="sxs-lookup"><span data-stu-id="ccc25-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="ccc25-114">La primera llamada, para obtener el tamaño del nombre, se conoce como modo de *consulta*.</span><span class="sxs-lookup"><span data-stu-id="ccc25-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc25-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccc25-115">Requirements</span></span>  
 <span data-ttu-id="ccc25-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccc25-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc25-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ccc25-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ccc25-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccc25-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccc25-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc25-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
