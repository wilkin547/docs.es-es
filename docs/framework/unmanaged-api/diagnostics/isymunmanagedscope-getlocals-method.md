---
description: 'Más información acerca de: ISymUnmanagedScope:: Getlocals ((método)'
title: ISymUnmanagedScope::GetLocals (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 6b20d8a79e826be0bd191d46e794f8dad45c4810
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763415"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="eee0b-103">ISymUnmanagedScope::GetLocals (Método)</span><span class="sxs-lookup"><span data-stu-id="eee0b-103">ISymUnmanagedScope::GetLocals Method</span></span>

<span data-ttu-id="eee0b-104">Obtiene las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="eee0b-104">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee0b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eee0b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eee0b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eee0b-106">Parameters</span></span>  

 `cLocals`  
 <span data-ttu-id="eee0b-107">de `ULONG32` Que indica el tamaño de la `locals` matriz.</span><span class="sxs-lookup"><span data-stu-id="eee0b-107">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="eee0b-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="eee0b-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="eee0b-109">enuncia La matriz que recibe las variables locales.</span><span class="sxs-lookup"><span data-stu-id="eee0b-109">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eee0b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eee0b-110">Return Value</span></span>  

 <span data-ttu-id="eee0b-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="eee0b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee0b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eee0b-112">Requirements</span></span>  

 <span data-ttu-id="eee0b-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="eee0b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee0b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="eee0b-114">See also</span></span>

- [<span data-ttu-id="eee0b-115">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eee0b-115">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
