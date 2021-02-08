---
description: 'Más información acerca de: ISymUnmanagedAsyncMethodPropertiesWriter::D efineKickoffMethod (método)'
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 7333823bce27eace4e9cb988ac31252743cca952
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790235"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="39b09-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="39b09-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="39b09-104">Establece el método de inicio que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="39b09-104">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b09-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39b09-105">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39b09-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39b09-106">Parameters</span></span>  
  
|<span data-ttu-id="39b09-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="39b09-107">Parameter</span></span>|<span data-ttu-id="39b09-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="39b09-108">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="39b09-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="39b09-109">Return Value</span></span>  

 <span data-ttu-id="39b09-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="39b09-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39b09-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39b09-111">Requirements</span></span>  

 <span data-ttu-id="39b09-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="39b09-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b09-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="39b09-113">See also</span></span>

- [<span data-ttu-id="39b09-114">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="39b09-114">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
