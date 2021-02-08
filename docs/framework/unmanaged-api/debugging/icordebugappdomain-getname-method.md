---
description: 'Más información acerca de: ICorDebugAppDomain:: GetName (método)'
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
ms.openlocfilehash: 56995f544e1576534e35b899a659ed409972305f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772437"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="276eb-103">ICorDebugAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="276eb-103">ICorDebugAppDomain::GetName Method</span></span>

<span data-ttu-id="276eb-104">Obtiene el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="276eb-104">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="276eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="276eb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="276eb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="276eb-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="276eb-107">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="276eb-107">[in] The size of the `szName` array.</span></span> <span data-ttu-id="276eb-108">Establezca este valor en cero para poner este método en modo de consulta.</span><span class="sxs-lookup"><span data-stu-id="276eb-108">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="276eb-109">enuncia Puntero al tamaño del nombre o número de caracteres devueltos realmente en `szName` .</span><span class="sxs-lookup"><span data-stu-id="276eb-109">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="276eb-110">En el modo de consulta, este valor permite que el autor de la llamada sepa el tamaño de un búfer que se va a asignar al nombre.</span><span class="sxs-lookup"><span data-stu-id="276eb-110">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="276eb-111">enuncia Matriz que almacena el nombre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="276eb-111">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="276eb-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="276eb-112">Remarks</span></span>  

 <span data-ttu-id="276eb-113">Un depurador llama al `GetName` método una vez para obtener el tamaño de un búfer necesario para el nombre.</span><span class="sxs-lookup"><span data-stu-id="276eb-113">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="276eb-114">El depurador asigna el búfer y, a continuación, llama al método una segunda vez para rellenar el búfer.</span><span class="sxs-lookup"><span data-stu-id="276eb-114">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="276eb-115">La primera llamada, para obtener el tamaño del nombre, se conoce como modo de *consulta*.</span><span class="sxs-lookup"><span data-stu-id="276eb-115">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="276eb-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="276eb-116">Requirements</span></span>  

 <span data-ttu-id="276eb-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="276eb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="276eb-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="276eb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="276eb-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="276eb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="276eb-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="276eb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
