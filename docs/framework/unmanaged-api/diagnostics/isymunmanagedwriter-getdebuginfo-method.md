---
description: 'Más información acerca de: ISymUnmanagedWriter:: GetDebugInfo (método)'
title: ISymUnmanagedWriter::GetDebugInfo (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 2255cc90c0bfcd36dacdf81703af67d3f47739db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762323"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="b793d-103">ISymUnmanagedWriter::GetDebugInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="b793d-103">ISymUnmanagedWriter::GetDebugInfo Method</span></span>

<span data-ttu-id="b793d-104">Devuelve la información necesaria para que un compilador escriba la entrada del directorio de depuración en el encabezado de archivo portable ejecutable (PE).</span><span class="sxs-lookup"><span data-stu-id="b793d-104">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="b793d-105">El escritor de símbolos rellena todos los campos excepto `TimeDateStamp` y `PointerToRawData` .</span><span class="sxs-lookup"><span data-stu-id="b793d-105">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="b793d-106">(El compilador es responsable de establecer estos dos campos de forma adecuada).</span><span class="sxs-lookup"><span data-stu-id="b793d-106">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="b793d-107">Un compilador debe llamar a este método, emitir el BLOB de datos al archivo PE, establecer el `PointerToRawData` campo del IMAGE_DEBUG_DIRECTORY para que apunte a los datos emitidos y escribir el IMAGE_DEBUG_DIRECTORY en el archivo PE.</span><span class="sxs-lookup"><span data-stu-id="b793d-107">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="b793d-108">El compilador también debe establecer el `TimeDateStamp` campo en el mismo valor del `TimeDateStamp` archivo PE que se está generando.</span><span class="sxs-lookup"><span data-stu-id="b793d-108">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b793d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b793d-109">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b793d-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b793d-110">Parameters</span></span>  

 `pIDD`  
 <span data-ttu-id="b793d-111">[in, out] Un puntero a un IMAGE_DEBUG_DIRECTORY que el escritor de símbolos rellenará.</span><span class="sxs-lookup"><span data-stu-id="b793d-111">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="b793d-112">de Un `DWORD` que contiene el tamaño de los datos de depuración.</span><span class="sxs-lookup"><span data-stu-id="b793d-112">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="b793d-113">enuncia Un puntero a un `DWORD` que recibe el tamaño del búfer necesario para contener los datos de depuración.</span><span class="sxs-lookup"><span data-stu-id="b793d-113">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="b793d-114">enuncia Un puntero a un búfer que es lo suficientemente grande como para contener los datos de depuración para el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="b793d-114">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b793d-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b793d-115">Return Value</span></span>  

 <span data-ttu-id="b793d-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b793d-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b793d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b793d-117">Requirements</span></span>  

 <span data-ttu-id="b793d-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b793d-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b793d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b793d-119">See also</span></span>

- [<span data-ttu-id="b793d-120">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b793d-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
