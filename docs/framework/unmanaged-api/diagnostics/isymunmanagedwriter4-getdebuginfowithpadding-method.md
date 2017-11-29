---
title: "ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f2f0aad37fcd63e2345cd32a00b44412ed8c7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="82373-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)</span><span class="sxs-lookup"><span data-stu-id="82373-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="82373-103">Funciona igual que [GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) excepto en que la cadena de ruta de acceso se rellena con ceros que siguen el carácter nulo de terminación para que los datos de cadena de un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="82373-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="82373-104">Relleno solo se proporciona si la longitud de cadena de ruta de acceso propio es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="82373-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="82373-105">Esto facilita la escritura herramientas que los archivos PE de diferencia.</span><span class="sxs-lookup"><span data-stu-id="82373-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82373-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82373-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82373-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82373-107">Parameters</span></span>  
  
|<span data-ttu-id="82373-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="82373-108">Parameter</span></span>|<span data-ttu-id="82373-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="82373-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="82373-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82373-110">Return Value</span></span>  
 <span data-ttu-id="82373-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="82373-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82373-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82373-112">Requirements</span></span>  
 <span data-ttu-id="82373-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82373-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82373-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="82373-114">See Also</span></span>  
 [<span data-ttu-id="82373-115">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82373-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
