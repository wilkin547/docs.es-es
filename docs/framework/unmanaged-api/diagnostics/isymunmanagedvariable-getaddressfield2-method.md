---
title: ISymUnmanagedVariable::GetAddressField2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
ms.openlocfilehash: 6256d052780b1c610e61267be2517954d722a42d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610605"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="13030-102">ISymUnmanagedVariable::GetAddressField2 (Método)</span><span class="sxs-lookup"><span data-stu-id="13030-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="13030-103">Obtiene el segundo campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="13030-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="13030-104">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="13030-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13030-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13030-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13030-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13030-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="13030-107">enuncia Un puntero a un `ULONG32` que recibe el segundo campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="13030-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13030-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13030-108">Return Value</span></span>  
 <span data-ttu-id="13030-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="13030-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13030-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13030-110">Requirements</span></span>  
 <span data-ttu-id="13030-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="13030-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13030-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="13030-112">See also</span></span>

- [<span data-ttu-id="13030-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13030-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="13030-114">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="13030-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="13030-115">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="13030-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="13030-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="13030-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
