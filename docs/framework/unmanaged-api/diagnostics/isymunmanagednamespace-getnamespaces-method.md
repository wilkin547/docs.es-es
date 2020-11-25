---
title: ISymUnmanagedNamespace::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
ms.openlocfilehash: 8eef973c4c054b704b7c3f798e5dc1aa455dda96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707781"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="e8923-102">ISymUnmanagedNamespace::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="e8923-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>

<span data-ttu-id="e8923-103">Obtiene los elementos secundarios de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8923-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8923-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8923-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8923-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8923-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="e8923-106">de `ULONG32` Que indica el tamaño de la `namespaces` matriz.</span><span class="sxs-lookup"><span data-stu-id="e8923-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="e8923-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8923-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="e8923-108">enuncia Puntero al búfer que contiene los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="e8923-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8923-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e8923-109">Return Value</span></span>  

 <span data-ttu-id="e8923-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e8923-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8923-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8923-111">Requirements</span></span>  

 <span data-ttu-id="e8923-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e8923-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8923-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8923-113">See also</span></span>

- [<span data-ttu-id="e8923-114">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8923-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
