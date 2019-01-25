---
title: ISymUnmanagedVariable::GetAttributes (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d418a1088f9ee23a088ab4c8246810d2c9bee4fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574344"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="d5f5a-102">ISymUnmanagedVariable::GetAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="d5f5a-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="d5f5a-103">Obtiene los marcadores de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="d5f5a-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5f5a-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5f5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5f5a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d5f5a-106">[out] Un puntero a un `ULONG32` que recibe los atributos.</span><span class="sxs-lookup"><span data-stu-id="d5f5a-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="d5f5a-107">El valor devuelto será uno de los valores definidos en el [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="d5f5a-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5f5a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5f5a-108">Return Value</span></span>  
 <span data-ttu-id="d5f5a-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d5f5a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5f5a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5f5a-110">Requirements</span></span>  
 <span data-ttu-id="d5f5a-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5f5a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f5a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5f5a-112">See also</span></span>
- [<span data-ttu-id="d5f5a-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5f5a-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
