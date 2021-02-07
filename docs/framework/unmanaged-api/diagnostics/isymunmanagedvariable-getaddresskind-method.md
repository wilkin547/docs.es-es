---
description: 'Más información sobre: ISymUnmanagedVariable:: GetAddressKind ((método)'
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
ms.openlocfilehash: 4b090560335432ad39157fee987ce15728fece63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762856"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="98ef9-103">ISymUnmanagedVariable::GetAddressKind (Método)</span><span class="sxs-lookup"><span data-stu-id="98ef9-103">ISymUnmanagedVariable::GetAddressKind Method</span></span>

<span data-ttu-id="98ef9-104">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="98ef9-104">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ef9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98ef9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98ef9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98ef9-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="98ef9-107">enuncia Un puntero a un `ULONG32` que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="98ef9-107">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="98ef9-108">Los valores posibles se definen en la enumeración [corsymaddrkind (](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="98ef9-108">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98ef9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98ef9-109">Return Value</span></span>  

 <span data-ttu-id="98ef9-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="98ef9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ef9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98ef9-111">Requirements</span></span>  

 <span data-ttu-id="98ef9-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="98ef9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ef9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="98ef9-113">See also</span></span>

- [<span data-ttu-id="98ef9-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98ef9-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
