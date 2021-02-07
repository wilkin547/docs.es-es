---
description: 'Más información acerca de: ISymUnmanagedReader:: Getnamespaces ((método)'
title: ISymUnmanagedReader::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
ms.openlocfilehash: 47f7bff829ca2a52eb95d7d7693a7486301de092
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764013"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="7b445-103">ISymUnmanagedReader::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="7b445-103">ISymUnmanagedReader::GetNamespaces Method</span></span>

<span data-ttu-id="7b445-104">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7b445-104">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b445-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b445-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b445-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b445-106">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="7b445-107">de Tamaño de la matriz de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="7b445-107">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="7b445-108">enuncia Puntero a una variable que recibe la longitud de la lista de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="7b445-108">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="7b445-109">enuncia Puntero a una variable que recibe la lista de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="7b445-109">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b445-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7b445-110">Return Value</span></span>  

 <span data-ttu-id="7b445-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7b445-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b445-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b445-112">Requirements</span></span>  

 <span data-ttu-id="7b445-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7b445-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b445-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b445-114">See also</span></span>

- [<span data-ttu-id="7b445-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b445-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
