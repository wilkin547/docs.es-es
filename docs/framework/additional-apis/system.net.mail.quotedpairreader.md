---
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
ms.openlocfilehash: 898c6e9d2d5dd02f3d5f9c096ad470b5dd445d1d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051316"
---
# <a name="quotedpairreader-class"></a><span data-ttu-id="767e9-102">Clase QuotedPairReader</span><span class="sxs-lookup"><span data-stu-id="767e9-102">QuotedPairReader class</span></span>

<span data-ttu-id="767e9-103">Determina qué caracteres están entre comillas (con escape) en una cadena entrecomillada.</span><span class="sxs-lookup"><span data-stu-id="767e9-103">Determines which characters are quoted (escaped) in a quoted string.</span></span> <span data-ttu-id="767e9-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="767e9-104">This class cannot be inherited.</span></span>

```csharp
internal static class QuotedPairReader
```

> [!WARNING]
> <span data-ttu-id="767e9-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="767e9-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="767e9-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="767e9-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="countquotedchars-method"></a><span data-ttu-id="767e9-107">Método CountQuotedChars</span><span class="sxs-lookup"><span data-stu-id="767e9-107">CountQuotedChars method</span></span>

<span data-ttu-id="767e9-108">Cuenta el número de caracteres entre comillas consecutivos, incluidas varias barras diagonales inversas anteriores, en la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="767e9-108">Counts the number of consecutive quoted characters, including multiple preceding quoted backslashes, in the specified string.</span></span> <span data-ttu-id="767e9-109">Por ejemplo, dada la cadena `a\\\b` y un índice de `4` , el método devuelve `4` , porque `b` está entre comillas y, por tanto, son las tres barras diagonales inversas anteriores.</span><span class="sxs-lookup"><span data-stu-id="767e9-109">For example, given the string `a\\\b` and an index of `4`, the method returns `4`, because `b` is quoted and so are the three preceding backslashes.</span></span>

```csharp
internal static int CountQuotedChars(string data, int index, bool permitUnicodeEscaping)
```

### <a name="parameters"></a><span data-ttu-id="767e9-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="767e9-110">Parameters</span></span>

- <span data-ttu-id="767e9-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="767e9-111">`data` <xref:System.String></span></span>

  <span data-ttu-id="767e9-112">Cadena de datos en la que se van a contar los caracteres comillas consecutivos.</span><span class="sxs-lookup"><span data-stu-id="767e9-112">The data string in which to count consecutive quoted characters.</span></span>

- <span data-ttu-id="767e9-113">`index` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="767e9-113">`index` <xref:System.Int32></span></span>

  <span data-ttu-id="767e9-114">Posición en la cadena especificada hasta e incluidos los caracteres consecutivos que se deben contar.</span><span class="sxs-lookup"><span data-stu-id="767e9-114">The position in the specified string up to and including which consecutive quoted characters should be counted.</span></span>

- <span data-ttu-id="767e9-115">`permitUnicodeEscaping` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="767e9-115">`permitUnicodeEscaping` <xref:System.Boolean></span></span>

  <span data-ttu-id="767e9-116">`true`para permitir el escape de caracteres Unicode; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="767e9-116">`true` to permit Unicode characters to be escaped; otherwise, `false`.</span></span>

### <a name="return-value"></a><span data-ttu-id="767e9-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="767e9-117">Return value</span></span>

<xref:System.Int32?displayProperty=nameWithType>

<span data-ttu-id="767e9-118">`0`Si el carácter que se encuentra en el índice especificado no tiene escape; de lo contrario, el número de caracteres consecutivos consecutivos hasta el carácter situado en `index` .</span><span class="sxs-lookup"><span data-stu-id="767e9-118">`0` if the character at the specified index is not escaped; otherwise, the number of consecutive quoted characters up to and including the character at `index`.</span></span>

### <a name="exceptions"></a><span data-ttu-id="767e9-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="767e9-119">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="767e9-120">Se encontró un carácter Unicode con escape, pero no está permitido.</span><span class="sxs-lookup"><span data-stu-id="767e9-120">An escaped Unicode character was found but is not permitted.</span></span>

## <a name="requirements"></a><span data-ttu-id="767e9-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="767e9-121">Requirements</span></span>

<span data-ttu-id="767e9-122">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="767e9-122">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="767e9-123">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="767e9-123">**Assembly:** System (in System.dll)</span></span>
