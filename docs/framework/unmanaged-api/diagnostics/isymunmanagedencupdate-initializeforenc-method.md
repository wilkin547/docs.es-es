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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46daf47e8fd478926ff75fa695f277c692679fb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424968"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="638eb-102">ISymUnmanagedENCUpdate::InitializeForEnc (Método)</span><span class="sxs-lookup"><span data-stu-id="638eb-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="638eb-103">Permite a los límites del método que debe calcularse antes de la primera llamada a la [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="638eb-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="638eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="638eb-104">Syntax</span></span>  
  
```  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="638eb-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="638eb-105">Return Value</span></span>  
 <span data-ttu-id="638eb-106">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="638eb-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="638eb-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="638eb-107">Requirements</span></span>  
 <span data-ttu-id="638eb-108">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="638eb-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="638eb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="638eb-109">See Also</span></span>  
 [<span data-ttu-id="638eb-110">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="638eb-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
