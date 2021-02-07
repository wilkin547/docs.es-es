---
description: 'Más información sobre: ISymUnmanagedENCUpdate:: Getlocalvariables ((método)'
title: ISymUnmanagedENCUpdate::GetLocalVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: bc034603dd6a09ea78dad789e11ea951d65e839b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721468"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="5d746-103">ISymUnmanagedENCUpdate::GetLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="5d746-103">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>

<span data-ttu-id="5d746-104">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="5d746-104">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d746-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d746-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d746-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d746-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="5d746-107">de Símbolo (token) de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="5d746-107">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="5d746-108">de `ULONG` Que indica el tamaño del `rgLocals` parámetro.</span><span class="sxs-lookup"><span data-stu-id="5d746-108">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="5d746-109">enuncia Matriz de instancias de [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="5d746-109">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5d746-110">enuncia Un puntero a un `ULONG` que recibe el tamaño del `rgLocals` búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="5d746-110">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d746-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d746-111">Return Value</span></span>  

 <span data-ttu-id="5d746-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5d746-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d746-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d746-113">Requirements</span></span>  

 <span data-ttu-id="5d746-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5d746-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d746-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d746-115">See also</span></span>

- [<span data-ttu-id="5d746-116">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d746-116">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
