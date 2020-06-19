---
title: Clase QuotedPairReader (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.QuotedPairReader
- System.Net.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 9b0bf835a34eecc651894f4336648b73a81b665c
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990503"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="b7072-102">Clase QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="b7072-102">QuotedPairReader class</span></span>

<span data-ttu-id="b7072-103">Determina qué caracteres están entre comillas (con escape) en una cadena entrecomillada.</span><span class="sxs-lookup"><span data-stu-id="b7072-103">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="b7072-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="b7072-104">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="b7072-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="b7072-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b7072-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="b7072-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="b7072-107">Método CountQuotedChars</span><span class="sxs-lookup"><span data-stu-id="b7072-107">CountQuotedChars method</span></span>

<span data-ttu-id="b7072-108">Cuenta el número de caracteres entre comillas consecutivos, incluidas varias barras diagonales inversas anteriores, en la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="b7072-108">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="b7072-109">Por ejemplo, dada la cadena `a\\\b` y un índice de `4` , el método devuelve `4` , porque `b` está entre comillas y, por tanto, son las tres barras diagonales inversas anteriores.</span><span class="sxs-lookup"><span data-stu-id="b7072-109">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="b7072-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7072-110">Parameters</span></span>

- <span data-ttu-id="b7072-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="b7072-111">`data` <xref:System.String></span></span>

  <span data-ttu-id="b7072-112">Cadena de datos en la que se van a contar los caracteres comillas consecutivos.</span><span class="sxs-lookup"><span data-stu-id="b7072-112">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="b7072-113">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="b7072-113">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="b7072-114">Posición en la cadena especificada hasta e incluidos los caracteres consecutivos que se deben contar.</span><span class="sxs-lookup"><span data-stu-id="b7072-114">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="b7072-115">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="b7072-115">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="b7072-116">`true`para permitir el escape de caracteres Unicode; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="b7072-116">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="b7072-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7072-117">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="b7072-118">`0`Si el carácter que se encuentra en el índice especificado no tiene escape; de lo contrario, el número de caracteres consecutivos consecutivos hasta el carácter situado en `index` .</span><span class="sxs-lookup"><span data-stu-id="b7072-118">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="b7072-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="b7072-119">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="b7072-120">Se encontró un carácter Unicode con escape, pero no está permitido.</span><span class="sxs-lookup"><span data-stu-id="b7072-120">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7072-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7072-121">Requirements</span></span>

<span data-ttu-id="b7072-122">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b7072-122">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b7072-123">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="b7072-123">**Assembly:** System (in System.dll)</span></span>
