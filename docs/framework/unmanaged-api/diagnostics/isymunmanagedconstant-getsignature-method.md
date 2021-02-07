---
description: 'Más información sobre: ISymUnmanagedConstant:: Getsignature ((método)'
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
ms.openlocfilehash: d28051c9d0e2675e980926fe63ffa7c4d13ef13a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689799"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="4263a-103">ISymUnmanagedConstant::GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="4263a-103">ISymUnmanagedConstant::GetSignature Method</span></span>

<span data-ttu-id="4263a-104">Obtiene la firma de la constante.</span><span class="sxs-lookup"><span data-stu-id="4263a-104">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4263a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4263a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4263a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4263a-106">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="4263a-107">de Longitud del búfer al que apunta el `pcSig` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4263a-107">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="4263a-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la firma.</span><span class="sxs-lookup"><span data-stu-id="4263a-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="4263a-109">enuncia Búfer que almacena la firma.</span><span class="sxs-lookup"><span data-stu-id="4263a-109">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4263a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4263a-110">Return Value</span></span>  

 <span data-ttu-id="4263a-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4263a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4263a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4263a-112">Requirements</span></span>  

 <span data-ttu-id="4263a-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4263a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4263a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4263a-114">See also</span></span>

- [<span data-ttu-id="4263a-115">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4263a-115">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="4263a-116">Método GetName</span><span class="sxs-lookup"><span data-stu-id="4263a-116">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="4263a-117">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="4263a-117">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
