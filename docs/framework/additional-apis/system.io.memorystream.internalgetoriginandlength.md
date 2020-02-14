---
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
ms.openlocfilehash: d82b5080e9fbd5fc6603f1cddae996c75a06d3a3
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215462"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="c5ba9-102">MemoryStream. InternalGetOriginAndLength (método)</span><span class="sxs-lookup"><span data-stu-id="c5ba9-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="c5ba9-103">Obtiene los valores internos del origen y la longitud de la secuencia de memoria.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="c5ba9-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5ba9-104">Parameters</span></span>

- <span data-ttu-id="c5ba9-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="c5ba9-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="c5ba9-106">Cuando este método devuelve, el desplazamiento de la matriz de bytes especificada al crear un nuevo objeto <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="c5ba9-107">Contiene 0 si la matriz de bytes se creó mediante <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="c5ba9-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="c5ba9-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="c5ba9-109">Cuando este método devuelve, el número de bytes dentro de la secuencia de memoria.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5ba9-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5ba9-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="c5ba9-111">El método `MemoryStream.InternalGetOriginAndLength` es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="c5ba9-112">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="c5ba9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5ba9-113">Requirements</span></span>

<span data-ttu-id="c5ba9-114">**Espacio de nombres:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="c5ba9-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="c5ba9-115">**Ensamblado:** mscorlib. dll (en mscorlib. dll)</span><span class="sxs-lookup"><span data-stu-id="c5ba9-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="c5ba9-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="c5ba9-116">**.NET Framework versions:** Available since 2.0.</span></span>
