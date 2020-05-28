---
title: CorOpenFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: 7318a7ea3eb1ddb047a799e58ebdfd9ce6cd76d1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007590"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="e2212-102">CorOpenFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e2212-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="e2212-103">Contiene valores de marca que controlan el comportamiento de los metadatos al abrir archivos de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="e2212-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2212-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2212-104">Syntax</span></span>  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e2212-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e2212-105">Members</span></span>  
  
|<span data-ttu-id="e2212-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e2212-106">Member</span></span>|<span data-ttu-id="e2212-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2212-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="e2212-108">Indica que el archivo se debe abrir solo para lectura.</span><span class="sxs-lookup"><span data-stu-id="e2212-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="e2212-109">Indica que el archivo se debe abrir para escritura.</span><span class="sxs-lookup"><span data-stu-id="e2212-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="e2212-110">Si usa la marca `ofWrite` al abrir un archivo .winmd, debe pasar también la marca `ofNoTransform`.</span><span class="sxs-lookup"><span data-stu-id="e2212-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="e2212-111">Máscara para lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="e2212-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="e2212-112">Indica que el archivo se debe leer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="e2212-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="e2212-113">Los metadatos deben mantener su propia copia.</span><span class="sxs-lookup"><span data-stu-id="e2212-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="e2212-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e2212-114">Obsolete.</span></span> <span data-ttu-id="e2212-115">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="e2212-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="e2212-116">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e2212-116">Obsolete.</span></span> <span data-ttu-id="e2212-117">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="e2212-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="e2212-118">Indica que el archivo se debe abrir para lectura y que no se puede realizar una llamada a `QueryInterface` para [IMetaDataEmit](imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e2212-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="e2212-119">Indica que la memoria se asignó mediante una llamada a [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) y que los metadatos liberarán.</span><span class="sxs-lookup"><span data-stu-id="e2212-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="e2212-120">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e2212-120">Obsolete.</span></span> <span data-ttu-id="e2212-121">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="e2212-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="e2212-122">Indica que se deben deshabilitar las transformaciones automáticas de archivos .winmd.</span><span class="sxs-lookup"><span data-stu-id="e2212-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="e2212-123">En otras palabras, se debe deshabilitar la proyección de un tipo de Windows Runtime en un tipo de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2212-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="e2212-124">Para obtener más información, vea [Windows Runtime y CLR: debajo del capó con .net y el Windows Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span><span class="sxs-lookup"><span data-stu-id="e2212-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="e2212-125">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e2212-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="e2212-126">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e2212-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="e2212-127">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e2212-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2212-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2212-128">Requirements</span></span>  
 <span data-ttu-id="e2212-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2212-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2212-130">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="e2212-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e2212-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2212-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2212-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e2212-132">See also</span></span>

- [<span data-ttu-id="e2212-133">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e2212-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
