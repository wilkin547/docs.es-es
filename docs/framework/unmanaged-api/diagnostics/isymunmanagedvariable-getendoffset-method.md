---
description: 'Más información sobre: ISymUnmanagedVariable:: Getendoffset ((método)'
title: ISymUnmanagedVariable::GetEndOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: 302f19c0d9fce1864e94a79efe3a3d1515478c0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762804"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="2bdb0-103">ISymUnmanagedVariable::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="2bdb0-103">ISymUnmanagedVariable::GetEndOffset Method</span></span>

<span data-ttu-id="2bdb0-104">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="2bdb0-104">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="2bdb0-105">Si se trata de una variable local dentro de un ámbito, el desplazamiento final se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="2bdb0-105">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bdb0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bdb0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bdb0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bdb0-107">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="2bdb0-108">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="2bdb0-108">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bdb0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2bdb0-109">Return Value</span></span>  

 <span data-ttu-id="2bdb0-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2bdb0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bdb0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bdb0-111">Requirements</span></span>  

 <span data-ttu-id="2bdb0-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2bdb0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bdb0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bdb0-113">See also</span></span>

- [<span data-ttu-id="2bdb0-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bdb0-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="2bdb0-115">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="2bdb0-115">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
