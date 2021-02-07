---
description: 'Más información sobre: ISymUnmanagedVariable:: Getaddressfield3 ((método)'
title: ISymUnmanagedVariable::GetAddressField3 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: 286d8382857e941173c22a7aebe65adc22ab779b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762921"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="d3207-103">ISymUnmanagedVariable::GetAddressField3 (Método)</span><span class="sxs-lookup"><span data-stu-id="d3207-103">ISymUnmanagedVariable::GetAddressField3 Method</span></span>

<span data-ttu-id="d3207-104">Obtiene el tercer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="d3207-104">Gets the third address field for this variable.</span></span> <span data-ttu-id="d3207-105">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="d3207-105">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3207-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3207-106">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3207-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3207-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="d3207-108">enuncia Un puntero a un `ULONG32` que recibe el tercer campo de dirección.</span><span class="sxs-lookup"><span data-stu-id="d3207-108">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3207-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d3207-109">Return Value</span></span>  

 <span data-ttu-id="d3207-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d3207-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3207-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3207-111">Requirements</span></span>  

 <span data-ttu-id="d3207-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d3207-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3207-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3207-113">See also</span></span>

- [<span data-ttu-id="d3207-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3207-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="d3207-115">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="d3207-115">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="d3207-116">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="d3207-116">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="d3207-117">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="d3207-117">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
