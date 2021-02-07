---
description: 'Más información acerca de: ISymUnmanagedScope:: Getnamespaces ((método)'
title: ISymUnmanagedScope::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: 39b6507845e911cafc9b9ab38f7b67cdf1fdf2c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763350"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="0ef5e-103">ISymUnmanagedScope::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="0ef5e-103">ISymUnmanagedScope::GetNamespaces Method</span></span>

<span data-ttu-id="0ef5e-104">Obtiene los espacios de nombres que se usan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="0ef5e-104">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ef5e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ef5e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ef5e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0ef5e-106">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="0ef5e-107">[in] Tamaño de la matriz `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="0ef5e-107">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="0ef5e-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ef5e-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="0ef5e-109">enuncia Matriz que recibe los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0ef5e-109">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ef5e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ef5e-110">Return Value</span></span>  

 <span data-ttu-id="0ef5e-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0ef5e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ef5e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ef5e-112">Requirements</span></span>  

 <span data-ttu-id="0ef5e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0ef5e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ef5e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ef5e-114">See also</span></span>

- [<span data-ttu-id="0ef5e-115">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ef5e-115">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
