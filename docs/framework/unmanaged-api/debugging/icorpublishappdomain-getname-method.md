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
ms.openlocfilehash: e95f96847c6e069758362fb6febc28dc31911bc9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396295"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="8f508-102">ICorPublishAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="8f508-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="8f508-103">Obtiene el nombre del dominio de aplicación representado por este [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8f508-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f508-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f508-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f508-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f508-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8f508-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="8f508-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8f508-107">enuncia Puntero al número de caracteres anchos, incluido el carácter nulo, devuelto en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="8f508-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="8f508-108">enuncia Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="8f508-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f508-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f508-109">Remarks</span></span>  
 <span data-ttu-id="8f508-110">Si `szName` no es null, el `GetName` método copia hasta `cchName` caracteres (incluido el terminador null) en `szName` .</span><span class="sxs-lookup"><span data-stu-id="8f508-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="8f508-111">Si se devuelve un valor distinto de NULL en `pcchName` , el número real de caracteres del nombre (incluido el terminador nulo) se almacena en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="8f508-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="8f508-112">El `GetName` método devuelve un S_OK HRESULT independientemente del número de caracteres que se hayan copiado.</span><span class="sxs-lookup"><span data-stu-id="8f508-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f508-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f508-113">Requirements</span></span>  
 <span data-ttu-id="8f508-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f508-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f508-115">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="8f508-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8f508-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f508-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f508-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f508-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f508-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f508-118">See also</span></span>

- [<span data-ttu-id="8f508-119">ICorPublishAppDomain (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f508-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
