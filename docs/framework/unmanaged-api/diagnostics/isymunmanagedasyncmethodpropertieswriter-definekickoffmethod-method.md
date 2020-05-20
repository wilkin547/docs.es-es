---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441726"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="14dc1-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="14dc1-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="14dc1-103">Establece el método de inicio que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="14dc1-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14dc1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14dc1-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14dc1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14dc1-105">Parameters</span></span>  
  
|<span data-ttu-id="14dc1-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="14dc1-106">Parameter</span></span>|<span data-ttu-id="14dc1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="14dc1-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="14dc1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14dc1-108">Return Value</span></span>  
 <span data-ttu-id="14dc1-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="14dc1-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14dc1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14dc1-110">Requirements</span></span>  
 <span data-ttu-id="14dc1-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="14dc1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14dc1-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="14dc1-112">See also</span></span>

- [<span data-ttu-id="14dc1-113">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14dc1-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
