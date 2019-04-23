---
title: ISymUnmanagedReader::GetMethodVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5d4145e6c76cf95f2468a3f5ad59edcd310423e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160880"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="a93a8-102">ISymUnmanagedReader::GetMethodVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="a93a8-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="a93a8-103">Obtiene la versión del método.</span><span class="sxs-lookup"><span data-stu-id="a93a8-103">Gets the method version.</span></span> <span data-ttu-id="a93a8-104">La versión del método comienza en 1 y se incrementa cada vez que se vuelve a compilar el método.</span><span class="sxs-lookup"><span data-stu-id="a93a8-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="a93a8-105">Recompilación puede realizarse sin cambios en el método.</span><span class="sxs-lookup"><span data-stu-id="a93a8-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93a8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a93a8-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a93a8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a93a8-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="a93a8-108">[in] El método que se va a obtener la versión.</span><span class="sxs-lookup"><span data-stu-id="a93a8-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="a93a8-109">[out] Un puntero a una variable que recibe la versión del método.</span><span class="sxs-lookup"><span data-stu-id="a93a8-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a93a8-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a93a8-110">Return Value</span></span>  
 <span data-ttu-id="a93a8-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a93a8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a93a8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a93a8-112">Requirements</span></span>  
 <span data-ttu-id="a93a8-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a93a8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a93a8-114">See also</span></span>

- [<span data-ttu-id="a93a8-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a93a8-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
