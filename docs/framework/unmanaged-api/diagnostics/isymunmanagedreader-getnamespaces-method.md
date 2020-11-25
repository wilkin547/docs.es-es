---
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
ms.openlocfilehash: c90cd0d21eca6875d3dae32e4ca80cf42e6140b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720599"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="8e36e-102">ISymUnmanagedReader::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="8e36e-102">ISymUnmanagedReader::GetNamespaces Method</span></span>

<span data-ttu-id="8e36e-103">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="8e36e-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e36e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e36e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e36e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e36e-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="8e36e-106">de Tamaño de la matriz de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="8e36e-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="8e36e-107">enuncia Puntero a una variable que recibe la longitud de la lista de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="8e36e-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="8e36e-108">enuncia Puntero a una variable que recibe la lista de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="8e36e-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e36e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e36e-109">Return Value</span></span>  

 <span data-ttu-id="8e36e-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8e36e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e36e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e36e-111">Requirements</span></span>  

 <span data-ttu-id="8e36e-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8e36e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e36e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e36e-113">See also</span></span>

- [<span data-ttu-id="8e36e-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e36e-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
