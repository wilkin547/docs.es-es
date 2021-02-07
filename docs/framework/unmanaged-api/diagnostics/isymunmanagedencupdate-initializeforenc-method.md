---
description: 'Más información sobre: ISymUnmanagedENCUpdate:: Initializeforenc ((método)'
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
ms.openlocfilehash: 2b70554cc565f025dcf35e2a84523a5f9a6130f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710106"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="5d765-103">ISymUnmanagedENCUpdate::InitializeForEnc (Método)</span><span class="sxs-lookup"><span data-stu-id="5d765-103">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>

<span data-ttu-id="5d765-104">Permite calcular los límites de método antes de la primera llamada al método [ISymUnmanagedENCUpdate:: UpdateSymbolStore2 (](isymunmanagedencupdate-updatesymbolstore2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5d765-104">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d765-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d765-105">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5d765-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d765-106">Return Value</span></span>  

 <span data-ttu-id="5d765-107">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5d765-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d765-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d765-108">Requirements</span></span>  

 <span data-ttu-id="5d765-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5d765-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d765-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d765-110">See also</span></span>

- [<span data-ttu-id="5d765-111">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d765-111">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
