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
ms.openlocfilehash: 9e907450b4ae985ee30d9958eec8baba797b495a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728607"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="e8931-102">ISymUnmanagedENCUpdate::GetLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="e8931-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>

<span data-ttu-id="e8931-103">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="e8931-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8931-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8931-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8931-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8931-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="e8931-106">de Símbolo (token) de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="e8931-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="e8931-107">de `ULONG` Que indica el tamaño del `rgLocals` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e8931-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="e8931-108">enuncia Matriz de instancias de [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="e8931-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e8931-109">enuncia Un puntero a un `ULONG` que recibe el tamaño del `rgLocals` búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="e8931-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8931-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e8931-110">Return Value</span></span>  

 <span data-ttu-id="e8931-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e8931-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8931-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8931-112">Requirements</span></span>  

 <span data-ttu-id="e8931-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e8931-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8931-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8931-114">See also</span></span>

- [<span data-ttu-id="e8931-115">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8931-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
