---
title: ISymUnmanagedVariable::GetAddressField1 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: 253fd17178c03bc0c4d8ea031888a404ad56f876
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615285"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="f4d1e-102">ISymUnmanagedVariable::GetAddressField1 (Método)</span><span class="sxs-lookup"><span data-stu-id="f4d1e-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="f4d1e-103">Obtiene el primer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="f4d1e-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="f4d1e-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f4d1e-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d1e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4d1e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4d1e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4d1e-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f4d1e-107">enuncia Un puntero a un `ULONG32` que recibe el primer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f4d1e-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4d1e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4d1e-108">Return Value</span></span>  
 <span data-ttu-id="f4d1e-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f4d1e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d1e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4d1e-110">Requirements</span></span>  
 <span data-ttu-id="f4d1e-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f4d1e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d1e-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="f4d1e-112">See also</span></span>

- [<span data-ttu-id="f4d1e-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4d1e-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="f4d1e-114">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="f4d1e-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="f4d1e-115">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="f4d1e-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="f4d1e-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="f4d1e-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
