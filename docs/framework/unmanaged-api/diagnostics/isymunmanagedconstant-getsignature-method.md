---
title: ISymUnmanagedConstant::GetSignature (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 4436e4528c1dc486eb5c443c5a9467ac69a26c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706936"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="4d0bd-102">ISymUnmanagedConstant::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-102">ISymUnmanagedConstant::GetSignature Method</span></span>

<span data-ttu-id="4d0bd-103">Obtiene la firma de la constante.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d0bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d0bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d0bd-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="4d0bd-106">de Longitud del búfer al que apunta el `pcSig` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="4d0bd-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="4d0bd-108">enuncia Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d0bd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d0bd-109">Return Value</span></span>  

 <span data-ttu-id="4d0bd-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0bd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d0bd-111">Requirements</span></span>  

 <span data-ttu-id="4d0bd-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4d0bd-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d0bd-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d0bd-113">See also</span></span>

- [<span data-ttu-id="4d0bd-114">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="4d0bd-115">GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-115">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="4d0bd-116">GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
