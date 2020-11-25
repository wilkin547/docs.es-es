---
title: AddFile2 (Método)
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: cff6707496c7d9657796deb8bf6fa9165ff295a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717089"
---
# <a name="addfile2-method"></a><span data-ttu-id="a8d26-102">AddFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="a8d26-102">AddFile2 Method</span></span>

<span data-ttu-id="a8d26-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a8d26-103">Adds files to the assembly.</span></span> <span data-ttu-id="a8d26-104">También se puede usar para crear módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="a8d26-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8d26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8d26-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8d26-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8d26-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="a8d26-107">IDENTIFICADOR del ensamblado al que se agrega el archivo.</span><span class="sxs-lookup"><span data-stu-id="a8d26-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="a8d26-108">Nombre del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="a8d26-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a8d26-109">`FileDef`Marcas com+ como `ffContainsNoMetaData` y `ffWriteable` .</span><span class="sxs-lookup"><span data-stu-id="a8d26-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="a8d26-110">`dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="a8d26-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="a8d26-111">Interfaz para la interfaz de [interfaz IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a8d26-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="a8d26-112">Recibe el identificador del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="a8d26-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8d26-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a8d26-113">Return Value</span></span>  

 <span data-ttu-id="a8d26-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8d26-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8d26-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8d26-115">Requirements</span></span>  

 <span data-ttu-id="a8d26-116">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="a8d26-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d26-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8d26-117">See also</span></span>

- [<span data-ttu-id="a8d26-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8d26-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="a8d26-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8d26-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="a8d26-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a8d26-120">ALink API</span></span>](index.md)
