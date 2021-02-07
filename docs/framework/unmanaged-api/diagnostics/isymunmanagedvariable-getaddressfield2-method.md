---
description: 'Más información sobre: ISymUnmanagedVariable:: Getaddressfield2 ((método)'
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
ms.openlocfilehash: 5d9bc226bfc462157e66b1d8fb43762945cdc016
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762973"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="0fe86-103">ISymUnmanagedVariable::GetAddressField2 (Método)</span><span class="sxs-lookup"><span data-stu-id="0fe86-103">ISymUnmanagedVariable::GetAddressField2 Method</span></span>

<span data-ttu-id="0fe86-104">Obtiene el segundo campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="0fe86-104">Gets the second address field for this variable.</span></span> <span data-ttu-id="0fe86-105">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="0fe86-105">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe86-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fe86-106">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fe86-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fe86-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="0fe86-108">enuncia Un puntero a un `ULONG32` que recibe el segundo campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="0fe86-108">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fe86-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0fe86-109">Return Value</span></span>  

 <span data-ttu-id="0fe86-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0fe86-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe86-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fe86-111">Requirements</span></span>  

 <span data-ttu-id="0fe86-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0fe86-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe86-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fe86-113">See also</span></span>

- [<span data-ttu-id="0fe86-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fe86-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="0fe86-115">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="0fe86-115">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="0fe86-116">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="0fe86-116">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="0fe86-117">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="0fe86-117">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
