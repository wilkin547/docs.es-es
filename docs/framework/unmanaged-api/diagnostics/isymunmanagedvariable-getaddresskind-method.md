---
title: ISymUnmanagedVariable::GetAddressKind (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
ms.openlocfilehash: 6a7824949edc905a3edcd58f60d40f8b1a40c53c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726917"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="eca66-102">ISymUnmanagedVariable::GetAddressKind (Método)</span><span class="sxs-lookup"><span data-stu-id="eca66-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>

<span data-ttu-id="eca66-103">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="eca66-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eca66-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eca66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eca66-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="eca66-106">enuncia Un puntero a un `ULONG32` que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="eca66-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="eca66-107">Los valores posibles se definen en la enumeración [corsymaddrkind (](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="eca66-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eca66-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eca66-108">Return Value</span></span>  

 <span data-ttu-id="eca66-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="eca66-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eca66-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eca66-110">Requirements</span></span>  

 <span data-ttu-id="eca66-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eca66-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca66-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eca66-112">See also</span></span>

- [<span data-ttu-id="eca66-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eca66-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
