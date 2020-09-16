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
ms.openlocfilehash: e474cac6437413565a1ebddfa88c3e228fe59d41
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556354"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="705ff-102">CorOpenFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="705ff-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="705ff-103">Contiene valores de marca que controlan el comportamiento de los metadatos al abrir archivos de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="705ff-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="705ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="705ff-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="705ff-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="705ff-105">Members</span></span>  
  
|<span data-ttu-id="705ff-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="705ff-106">Member</span></span>|<span data-ttu-id="705ff-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="705ff-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="705ff-108">Indica que el archivo se debe abrir solo para lectura.</span><span class="sxs-lookup"><span data-stu-id="705ff-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="705ff-109">Indica que el archivo se debe abrir para escritura.</span><span class="sxs-lookup"><span data-stu-id="705ff-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="705ff-110">Si usa la marca `ofWrite` al abrir un archivo .winmd, debe pasar también la marca `ofNoTransform`.</span><span class="sxs-lookup"><span data-stu-id="705ff-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="705ff-111">Máscara para lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="705ff-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="705ff-112">Indica que el archivo se debe leer en la memoria.</span><span class="sxs-lookup"><span data-stu-id="705ff-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="705ff-113">Los metadatos deben mantener su propia copia.</span><span class="sxs-lookup"><span data-stu-id="705ff-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="705ff-114">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="705ff-114">Obsolete.</span></span> <span data-ttu-id="705ff-115">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="705ff-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="705ff-116">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="705ff-116">Obsolete.</span></span> <span data-ttu-id="705ff-117">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="705ff-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="705ff-118">Indica que el archivo se debe abrir para lectura y que no se puede realizar una llamada a `QueryInterface` para [IMetaDataEmit](imetadataemit-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="705ff-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="705ff-119">Indica que la memoria se asignó mediante una llamada a [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) y que los metadatos liberarán.</span><span class="sxs-lookup"><span data-stu-id="705ff-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="705ff-120">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="705ff-120">Obsolete.</span></span> <span data-ttu-id="705ff-121">Esta marca se omite.</span><span class="sxs-lookup"><span data-stu-id="705ff-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="705ff-122">Indica que se deben deshabilitar las transformaciones automáticas de archivos .winmd.</span><span class="sxs-lookup"><span data-stu-id="705ff-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="705ff-123">En otras palabras, se debe deshabilitar la proyección de un tipo de Windows Runtime en un tipo de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="705ff-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="705ff-124">Para obtener más información, vea [Windows Runtime y CLR: debajo del capó con .net y el Windows Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span><span class="sxs-lookup"><span data-stu-id="705ff-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="705ff-125">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="705ff-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="705ff-126">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="705ff-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="705ff-127">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="705ff-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="705ff-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="705ff-128">Requirements</span></span>  
 <span data-ttu-id="705ff-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="705ff-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="705ff-130">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="705ff-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="705ff-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="705ff-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705ff-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="705ff-132">See also</span></span>

- [<span data-ttu-id="705ff-133">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="705ff-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
