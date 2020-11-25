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
ms.openlocfilehash: d6b05333b9e02c4202c0fd9bdee9b5c055aa4da3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694365"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="c2f2e-102">ICorPublishAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="c2f2e-102">ICorPublishAppDomain::GetName Method</span></span>

<span data-ttu-id="c2f2e-103">Obtiene el nombre del dominio de aplicación representado por este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c2f2e-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2f2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2f2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2f2e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2f2e-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="c2f2e-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="c2f2e-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c2f2e-107">enuncia Puntero al número de caracteres anchos, incluido el carácter nulo, devuelto en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="c2f2e-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="c2f2e-108">enuncia Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="c2f2e-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2f2e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2f2e-109">Remarks</span></span>  

 <span data-ttu-id="c2f2e-110">Si `szName` no es null, el `GetName` método copia hasta `cchName` caracteres (incluido el terminador null) en `szName` .</span><span class="sxs-lookup"><span data-stu-id="c2f2e-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="c2f2e-111">Si se devuelve un valor distinto de NULL en `pcchName` , el número real de caracteres del nombre (incluido el terminador nulo) se almacena en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="c2f2e-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="c2f2e-112">El `GetName` método devuelve un S_OK HRESULT independientemente del número de caracteres que se hayan copiado.</span><span class="sxs-lookup"><span data-stu-id="c2f2e-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2f2e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2f2e-113">Requirements</span></span>  

 <span data-ttu-id="c2f2e-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2f2e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2f2e-115">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="c2f2e-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c2f2e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2f2e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2f2e-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2f2e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f2e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2f2e-118">See also</span></span>

- [<span data-ttu-id="c2f2e-119">ICorPublishAppDomain (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2f2e-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
