---
title: ISymUnmanagedVariable::GetSignature (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: 2939d9cf3991a9e0b8f93bb301925b1092eca50e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446049"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="db1e5-102">ISymUnmanagedVariable::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="db1e5-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="db1e5-103">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="db1e5-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db1e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db1e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db1e5-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="db1e5-106">de Longitud del búfer al que apunta el parámetro `sig`.</span><span class="sxs-lookup"><span data-stu-id="db1e5-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="db1e5-107">enuncia Puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="db1e5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="db1e5-108">enuncia Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="db1e5-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db1e5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db1e5-109">Return Value</span></span>  
 <span data-ttu-id="db1e5-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="db1e5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1e5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db1e5-111">Requirements</span></span>  
 <span data-ttu-id="db1e5-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="db1e5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1e5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="db1e5-113">See also</span></span>

- [<span data-ttu-id="db1e5-114">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db1e5-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
