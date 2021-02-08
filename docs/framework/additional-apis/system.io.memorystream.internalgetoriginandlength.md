---
description: 'Más información sobre: método MemoryStream. InternalGetOriginAndLength'
title: Método MemoryStream. InternalGetOriginAndLength (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 4232852c0835a43454f36271a43062e1240297a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802546"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="02491-103">Método MemoryStream.InternalGetOriginAndLength</span><span class="sxs-lookup"><span data-stu-id="02491-103">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="02491-104">Obtiene los valores internos del origen y la longitud de la secuencia de memoria.</span><span class="sxs-lookup"><span data-stu-id="02491-104">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="02491-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02491-105">Parameters</span></span>

- <span data-ttu-id="02491-106">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="02491-106">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="02491-107">Cuando este método devuelve, el desplazamiento de la matriz de bytes especificada al crear un nuevo <xref:System.IO.MemoryStream> objeto.</span><span class="sxs-lookup"><span data-stu-id="02491-107">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="02491-108">Contiene 0 si la matriz de bytes fue creada por <xref:System.IO.MemoryStream> .</span><span class="sxs-lookup"><span data-stu-id="02491-108">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="02491-109">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="02491-109">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="02491-110">Cuando este método devuelve, el número de bytes dentro de la secuencia de memoria.</span><span class="sxs-lookup"><span data-stu-id="02491-110">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="02491-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02491-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="02491-112">El `MemoryStream.InternalGetOriginAndLength` método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="02491-112">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="02491-113">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="02491-113">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="02491-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02491-114">Requirements</span></span>

<span data-ttu-id="02491-115">**Espacio de nombres:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="02491-115">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="02491-116">**Ensamblado:** mscorlib.dll (en mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="02491-116">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="02491-117">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="02491-117">**.NET Framework versions:** Available since 2.0.</span></span>
