---
description: 'Más información sobre: ISymUnmanagedNamespace:: Getnamespaces ((método)'
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
ms.openlocfilehash: f17b16e2a3a7001d16c86dd6dc95241c1b0785e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709911"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="b447e-103">ISymUnmanagedNamespace::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="b447e-103">ISymUnmanagedNamespace::GetNamespaces Method</span></span>

<span data-ttu-id="b447e-104">Obtiene los elementos secundarios de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b447e-104">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b447e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b447e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b447e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b447e-106">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="b447e-107">de `ULONG32` Que indica el tamaño de la `namespaces` matriz.</span><span class="sxs-lookup"><span data-stu-id="b447e-107">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="b447e-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b447e-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="b447e-109">enuncia Puntero al búfer que contiene los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b447e-109">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b447e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b447e-110">Return Value</span></span>  

 <span data-ttu-id="b447e-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b447e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b447e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b447e-112">Requirements</span></span>  

 <span data-ttu-id="b447e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b447e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b447e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b447e-114">See also</span></span>

- [<span data-ttu-id="b447e-115">ISymUnmanagedNamespace (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b447e-115">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
