---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707092"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="a9c8a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="a9c8a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="a9c8a-103">Establece el método de inicio que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="a9c8a-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9c8a-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c8a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9c8a-105">Parameters</span></span>  
  
|<span data-ttu-id="a9c8a-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a9c8a-106">Parameter</span></span>|<span data-ttu-id="a9c8a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9c8a-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="a9c8a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9c8a-108">Return Value</span></span>  

 <span data-ttu-id="a9c8a-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="a9c8a-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c8a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9c8a-110">Requirements</span></span>  

 <span data-ttu-id="a9c8a-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a9c8a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c8a-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9c8a-112">See also</span></span>

- [<span data-ttu-id="a9c8a-113">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9c8a-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
