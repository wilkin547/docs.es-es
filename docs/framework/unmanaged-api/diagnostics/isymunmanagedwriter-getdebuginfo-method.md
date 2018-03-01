---
title: "ISymUnmanagedWriter::GetDebugInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f071bfe88397d6431fb50403c3969d82c5cfe8fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="cf788-102">ISymUnmanagedWriter::GetDebugInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="cf788-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="cf788-103">Devuelve la información necesaria para que un compilador escribir la entrada de directorio de depuración en el encabezado del archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="cf788-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="cf788-104">El escritor de símbolos rellena todos los campos excepto `TimeDateStamp` y `PointerToRawData`.</span><span class="sxs-lookup"><span data-stu-id="cf788-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="cf788-105">(El compilador es responsable de establecer correctamente estos dos campos).</span><span class="sxs-lookup"><span data-stu-id="cf788-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="cf788-106">Un compilador debe llamar a este método, emitir el blob de datos en el archivo PE, establezca el `PointerToRawData` campo IMAGE_DEBUG_DIRECTORY para apuntar a los datos emitidos y escribir IMAGE_DEBUG_DIRECTORY en el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="cf788-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="cf788-107">El compilador también debe establecer el `TimeDateStamp` campo para igualar la `TimeDateStamp` del archivo PE que se está generando.</span><span class="sxs-lookup"><span data-stu-id="cf788-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf788-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf788-108">Syntax</span></span>  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf788-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf788-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="cf788-110">[entrada, salida] Un puntero a IMAGE_DEBUG_DIRECTORY que van a rellenar el escritor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="cf788-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="cf788-111">[in] Un `DWORD` que contiene el tamaño de los datos de depuración.</span><span class="sxs-lookup"><span data-stu-id="cf788-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="cf788-112">[out] Un puntero a un `DWORD` que recibe el tamaño del búfer necesario para contener los datos de depuración.</span><span class="sxs-lookup"><span data-stu-id="cf788-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="cf788-113">[out] Un puntero a un búfer que es lo suficientemente grande como para contener los datos de depuración para el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="cf788-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf788-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf788-114">Return Value</span></span>  
 <span data-ttu-id="cf788-115">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cf788-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf788-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf788-116">Requirements</span></span>  
 <span data-ttu-id="cf788-117">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cf788-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf788-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf788-118">See Also</span></span>  
 [<span data-ttu-id="cf788-119">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf788-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
