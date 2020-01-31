---
title: ICorPublishAppDomain::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790715"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="2ab22-102">ICorPublishAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="2ab22-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="2ab22-103">Obtiene el nombre del dominio de aplicación representado por este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2ab22-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab22-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ab22-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab22-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2ab22-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2ab22-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="2ab22-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2ab22-107">enuncia Puntero al número de caracteres anchos, incluido el carácter nulo, devuelto en la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="2ab22-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="2ab22-108">enuncia Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="2ab22-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ab22-109">Notas</span><span class="sxs-lookup"><span data-stu-id="2ab22-109">Remarks</span></span>  
 <span data-ttu-id="2ab22-110">Si `szName` no es null, el método `GetName` copia hasta `cchName` caracteres (incluido el terminador null) en `szName`.</span><span class="sxs-lookup"><span data-stu-id="2ab22-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="2ab22-111">Si se devuelve un valor distinto de NULL en `pcchName`, el número real de caracteres del nombre (incluido el terminador nulo) se almacena en la matriz de `szName`.</span><span class="sxs-lookup"><span data-stu-id="2ab22-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="2ab22-112">El método `GetName` devuelve un S_OK HRESULT independientemente del número de caracteres que se hayan copiado.</span><span class="sxs-lookup"><span data-stu-id="2ab22-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab22-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2ab22-113">Requirements</span></span>  
 <span data-ttu-id="2ab22-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab22-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab22-115">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2ab22-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2ab22-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ab22-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ab22-117">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab22-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab22-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ab22-118">See also</span></span>

- [<span data-ttu-id="2ab22-119">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ab22-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
