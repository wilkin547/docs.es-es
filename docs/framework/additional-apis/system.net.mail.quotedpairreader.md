---
description: 'Más información sobre: clase QuotedPairReader'
title: Clase QuotedPairReader (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.QuotedPairReader
- System.Net.Mail.QuotedPairReader.CountQuotedChars
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 810a7b02948a1b7aa542a179563af9a6d79dd763
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699667"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="47b5f-103">Clase QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="47b5f-103">QuotedPairReader class</span></span>

<span data-ttu-id="47b5f-104">Determina qué caracteres están entre comillas (con escape) en una cadena entrecomillada.</span><span class="sxs-lookup"><span data-stu-id="47b5f-104">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="47b5f-105">Esta clase no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="47b5f-105">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="47b5f-106">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="47b5f-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="47b5f-107">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="47b5f-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="47b5f-108">Método CountQuotedChars</span><span class="sxs-lookup"><span data-stu-id="47b5f-108">CountQuotedChars method</span></span>

<span data-ttu-id="47b5f-109">Cuenta el número de caracteres entre comillas consecutivos, incluidas varias barras diagonales inversas anteriores, en la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="47b5f-109">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="47b5f-110">Por ejemplo, dada la cadena `a\\\b` y un índice de `4` , el método devuelve `4` , porque `b` está entre comillas y, por tanto, son las tres barras diagonales inversas anteriores.</span><span class="sxs-lookup"><span data-stu-id="47b5f-110">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="47b5f-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47b5f-111">Parameters</span></span>

- <span data-ttu-id="47b5f-112">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="47b5f-112">`data` <xref:System.String></span></span>

  <span data-ttu-id="47b5f-113">Cadena de datos en la que se van a contar los caracteres comillas consecutivos.</span><span class="sxs-lookup"><span data-stu-id="47b5f-113">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="47b5f-114">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="47b5f-114">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="47b5f-115">Posición en la cadena especificada hasta e incluidos los caracteres consecutivos que se deben contar.</span><span class="sxs-lookup"><span data-stu-id="47b5f-115">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="47b5f-116">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="47b5f-116">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="47b5f-117">`true` para permitir el escape de caracteres Unicode; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="47b5f-117">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="47b5f-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47b5f-118">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="47b5f-119">`0` Si el carácter que se encuentra en el índice especificado no tiene escape; de lo contrario, el número de caracteres consecutivos consecutivos hasta el carácter situado en `index` .</span><span class="sxs-lookup"><span data-stu-id="47b5f-119">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="47b5f-120">Excepciones</span><span class="sxs-lookup"><span data-stu-id="47b5f-120">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="47b5f-121">Se encontró un carácter Unicode con escape, pero no está permitido.</span><span class="sxs-lookup"><span data-stu-id="47b5f-121">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="47b5f-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47b5f-122">Requirements</span></span>

<span data-ttu-id="47b5f-123">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="47b5f-123">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="47b5f-124">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="47b5f-124">**Assembly:** System (in System.dll)</span></span>
