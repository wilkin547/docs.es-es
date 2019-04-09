---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 191aa16c285b3a28beed65004d65525c9214ec93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081578"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="0f971-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)</span><span class="sxs-lookup"><span data-stu-id="0f971-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="0f971-103">Funciona igual que [GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros que siguen el carácter nulo de terminación para que los datos de cadena de un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="0f971-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="0f971-104">Relleno solo se da si la longitud de cadena de ruta de acceso propio es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="0f971-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="0f971-105">Esto facilita la escritura herramientas que los archivos PE de diferencia.</span><span class="sxs-lookup"><span data-stu-id="0f971-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f971-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f971-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f971-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f971-107">Parameters</span></span>  
  
|<span data-ttu-id="0f971-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="0f971-108">Parameter</span></span>|<span data-ttu-id="0f971-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f971-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="0f971-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f971-110">Return Value</span></span>  
 <span data-ttu-id="0f971-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0f971-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f971-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f971-112">Requirements</span></span>  
 <span data-ttu-id="0f971-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f971-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f971-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f971-114">See also</span></span>

- [<span data-ttu-id="0f971-115">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f971-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
