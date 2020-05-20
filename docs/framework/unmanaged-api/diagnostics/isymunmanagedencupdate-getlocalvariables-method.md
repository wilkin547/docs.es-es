---
title: ISymUnmanagedENCUpdate::GetLocalVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 5e5bf097a4b1e366fff807595b22c4696a91cf43
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614557"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="d04df-102">ISymUnmanagedENCUpdate::GetLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="d04df-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="d04df-103">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="d04df-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d04df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d04df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d04df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d04df-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="d04df-106">de Símbolo (token) de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="d04df-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="d04df-107">de `ULONG`Que indica el tamaño del `rgLocals` parámetro.</span><span class="sxs-lookup"><span data-stu-id="d04df-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="d04df-108">enuncia Matriz de instancias de [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="d04df-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d04df-109">enuncia Un puntero a un `ULONG` que recibe el tamaño del `rgLocals` búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="d04df-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d04df-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d04df-110">Return Value</span></span>  
 <span data-ttu-id="d04df-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d04df-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d04df-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d04df-112">Requirements</span></span>  
 <span data-ttu-id="d04df-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d04df-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04df-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d04df-114">See also</span></span>

- [<span data-ttu-id="d04df-115">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d04df-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
