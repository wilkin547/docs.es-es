---
description: 'Más información sobre: ISymUnmanagedVariable:: Getaddressfield1 ((método)'
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
ms.openlocfilehash: 1ff6862cef52ef8fcb449563198c2df1de356530
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762999"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="f7c6b-103">ISymUnmanagedVariable::GetAddressField1 (Método)</span><span class="sxs-lookup"><span data-stu-id="f7c6b-103">ISymUnmanagedVariable::GetAddressField1 Method</span></span>

<span data-ttu-id="f7c6b-104">Obtiene el primer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="f7c6b-104">Gets the first address field for this variable.</span></span> <span data-ttu-id="f7c6b-105">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f7c6b-105">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c6b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7c6b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c6b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7c6b-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="f7c6b-108">enuncia Un puntero a un `ULONG32` que recibe el primer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="f7c6b-108">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7c6b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7c6b-109">Return Value</span></span>  

 <span data-ttu-id="f7c6b-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f7c6b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c6b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7c6b-111">Requirements</span></span>  

 <span data-ttu-id="f7c6b-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f7c6b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c6b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7c6b-113">See also</span></span>

- [<span data-ttu-id="f7c6b-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7c6b-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="f7c6b-115">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="f7c6b-115">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="f7c6b-116">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="f7c6b-116">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="f7c6b-117">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="f7c6b-117">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
