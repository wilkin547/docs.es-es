---
title: ISymUnmanagedConstant::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c31f9bda2f1dfdb5d1f78055f53304352c5a660
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515344"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="1d8dd-102">ISymUnmanagedConstant::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="1d8dd-103">Obtiene el nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="1d8dd-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d8dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d8dd-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d8dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d8dd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1d8dd-106">[in] La longitud del búfer que el `szName` parámetro señala.</span><span class="sxs-lookup"><span data-stu-id="1d8dd-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1d8dd-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="1d8dd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="1d8dd-108">[out] Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="1d8dd-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d8dd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d8dd-109">Return Value</span></span>  
 <span data-ttu-id="1d8dd-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1d8dd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d8dd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d8dd-111">Requirements</span></span>  
 <span data-ttu-id="1d8dd-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1d8dd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d8dd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d8dd-113">See also</span></span>
- [<span data-ttu-id="1d8dd-114">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="1d8dd-115">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="1d8dd-116">GetValue (método)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
