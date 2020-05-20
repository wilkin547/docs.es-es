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
ms.openlocfilehash: 48c50ac6be6d525676d85578e5a55a27104c180a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615103"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="a0b3d-102">ISymUnmanagedNamespace::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="a0b3d-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="a0b3d-103">Obtiene los elementos secundarios de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0b3d-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0b3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b3d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0b3d-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="a0b3d-106">de `ULONG32`Que indica el tamaño de la `namespaces` matriz.</span><span class="sxs-lookup"><span data-stu-id="a0b3d-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="a0b3d-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0b3d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="a0b3d-108">enuncia Puntero al búfer que contiene los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0b3d-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0b3d-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0b3d-109">Return Value</span></span>  
 <span data-ttu-id="a0b3d-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a0b3d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b3d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0b3d-111">Requirements</span></span>  
 <span data-ttu-id="a0b3d-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a0b3d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b3d-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a0b3d-113">See also</span></span>

- [<span data-ttu-id="a0b3d-114">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0b3d-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
