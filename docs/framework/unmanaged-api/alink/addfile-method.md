---
title: AddFile (Método)
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446684"
---
# <a name="addfile-method"></a><span data-ttu-id="cab0b-102">AddFile (Método)</span><span class="sxs-lookup"><span data-stu-id="cab0b-102">AddFile Method</span></span>
<span data-ttu-id="cab0b-103">Agrega archivos al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cab0b-103">Adds files to the assembly.</span></span> <span data-ttu-id="cab0b-104">También se puede usar para crear módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="cab0b-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab0b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cab0b-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cab0b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cab0b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cab0b-107">IDENTIFICADOR único del ensamblado que se va a aumentar.</span><span class="sxs-lookup"><span data-stu-id="cab0b-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="cab0b-108">Nombre completo del archivo que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="cab0b-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cab0b-109">Marcas de FileDef COM+, como `ffContainsNoMetaData` y `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="cab0b-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="cab0b-110">`dwFlags` se pasa al [método definefile (](../metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="cab0b-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="cab0b-111">[IMetaDataEmit](../metadata/imetadataemit-interface.md) interfaz interface que se va a usar para emitir metadatos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="cab0b-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="cab0b-112">Puntero al lugar donde se almacenará el identificador único del archivo agregado.</span><span class="sxs-lookup"><span data-stu-id="cab0b-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cab0b-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cab0b-113">Return Value</span></span>  
 <span data-ttu-id="cab0b-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="cab0b-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cab0b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cab0b-115">Requirements</span></span>  
 <span data-ttu-id="cab0b-116">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="cab0b-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab0b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cab0b-117">See also</span></span>

- [<span data-ttu-id="cab0b-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cab0b-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cab0b-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cab0b-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cab0b-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="cab0b-120">ALink API</span></span>](index.md)
