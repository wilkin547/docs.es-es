---
title: ISymUnmanagedENCUpdate::InitializeForEnc (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
ms.openlocfilehash: 220788a38cd0ff90fed3b681a161c579206cf805
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449025"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="83ea0-102">ISymUnmanagedENCUpdate::InitializeForEnc (Método)</span><span class="sxs-lookup"><span data-stu-id="83ea0-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="83ea0-103">Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="83ea0-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ea0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83ea0-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="83ea0-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="83ea0-105">Return Value</span></span>  
 <span data-ttu-id="83ea0-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="83ea0-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ea0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83ea0-107">Requirements</span></span>  
 <span data-ttu-id="83ea0-108">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="83ea0-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ea0-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="83ea0-109">See also</span></span>

- [<span data-ttu-id="83ea0-110">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83ea0-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
