---
description: 'Más información sobre: IAssemblyCacheItem:: CreateStream ((método)'
title: IAssemblyCacheItem::CreateStream (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 89592d8fe1a7f43a7da20dd10883881c3339f088
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760880"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="d0461-103">IAssemblyCacheItem::CreateStream (Método)</span><span class="sxs-lookup"><span data-stu-id="d0461-103">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="d0461-104">Crea una secuencia con el nombre y el formato especificados.</span><span class="sxs-lookup"><span data-stu-id="d0461-104">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0461-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0461-105">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="d0461-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0461-106">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="d0461-107">de Marcas definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="d0461-107">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="d0461-108">de Nombre del flujo que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="d0461-108">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="d0461-109">de Formato del archivo que se va a transmitir por secuencias.</span><span class="sxs-lookup"><span data-stu-id="d0461-109">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="d0461-110">de Marcas específicas del formato definidas en Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="d0461-110">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="d0461-111">enuncia Puntero a la dirección de la instancia de [IStream](/windows/desktop/api/objidl/nn-objidl-istream) devuelta.</span><span class="sxs-lookup"><span data-stu-id="d0461-111">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="d0461-112">[in, Optional] Tamaño máximo de la secuencia a la que hace referencia `ppIStream` .</span><span class="sxs-lookup"><span data-stu-id="d0461-112">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0461-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0461-113">Requirements</span></span>

<span data-ttu-id="d0461-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0461-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d0461-115">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d0461-115">**Header:** Fusion.h</span></span>

<span data-ttu-id="d0461-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0461-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d0461-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0461-117">See also</span></span>

- [<span data-ttu-id="d0461-118">IAssemblyCacheItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0461-118">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
