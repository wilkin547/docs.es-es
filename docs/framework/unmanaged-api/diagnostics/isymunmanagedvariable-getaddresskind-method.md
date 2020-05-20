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
ms.openlocfilehash: 093c5e3e64395c8946acd9201990d132e8111fc7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610592"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="584f5-102">ISymUnmanagedVariable::GetAddressKind (Método)</span><span class="sxs-lookup"><span data-stu-id="584f5-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="584f5-103">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="584f5-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="584f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="584f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="584f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="584f5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="584f5-106">enuncia Un puntero a un `ULONG32` que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="584f5-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="584f5-107">Los valores posibles se definen en la enumeración [corsymaddrkind (](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="584f5-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="584f5-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="584f5-108">Return Value</span></span>  
 <span data-ttu-id="584f5-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="584f5-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="584f5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="584f5-110">Requirements</span></span>  
 <span data-ttu-id="584f5-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="584f5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="584f5-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="584f5-112">See also</span></span>

- [<span data-ttu-id="584f5-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="584f5-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
