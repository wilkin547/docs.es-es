---
title: Clase MailBnfHelper (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mime.MailBnfHelper
- System.Net.Mime.MailBnfHelper.Ascii7bitMaxValue
- System.Net.Mime.MailBnfHelper.Atext
- System.Net.Mime.MailBnfHelper.CR
- System.Net.Mime.MailBnfHelper.Ctext
- System.Net.Mime.MailBnfHelper.Dot
- System.Net.Mime.MailBnfHelper.EndComment
- System.Net.Mime.MailBnfHelper.LF
- System.Net.Mime.MailBnfHelper.Space
- System.Net.Mime.MailBnfHelper.StartComment
- System.Net.Mime.MailBnfHelper.Tab
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 86c98726a7886285917b6be8c7631ca1e9e425e6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990500"
---
# <a name="mailbnfhelper-class"></a><span data-ttu-id="663cb-102">Clase MailBnfHelper</span><span class="sxs-lookup"><span data-stu-id="663cb-102">MailBnfHelper class</span></span>

<span data-ttu-id="663cb-103">Contiene métodos de utilidad para analizar las cadenas con formato de mensajes de Internet.</span><span class="sxs-lookup"><span data-stu-id="663cb-103">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="663cb-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="663cb-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="663cb-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="663cb-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="663cb-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="663cb-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="663cb-107">Campo Ascii7bitMaxValue</span><span class="sxs-lookup"><span data-stu-id="663cb-107">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="663cb-108">Representa el valor ASCII máximo de 7 bits.</span><span class="sxs-lookup"><span data-stu-id="663cb-108">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="663cb-109">Campo texto</span><span class="sxs-lookup"><span data-stu-id="663cb-109">Atext field</span></span>

<span data-ttu-id="663cb-110">Representa los caracteres permitidos en los átomos.</span><span class="sxs-lookup"><span data-stu-id="663cb-110">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="663cb-111">Campo CR</span><span class="sxs-lookup"><span data-stu-id="663cb-111">CR field</span></span>

<span data-ttu-id="663cb-112">Representa el carácter de retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="663cb-112">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="663cb-113">Campo Ctext</span><span class="sxs-lookup"><span data-stu-id="663cb-113">Ctext field</span></span>

<span data-ttu-id="663cb-114">Representa los caracteres permitidos dentro de los comentarios.</span><span class="sxs-lookup"><span data-stu-id="663cb-114">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="663cb-115">Campo de punto</span><span class="sxs-lookup"><span data-stu-id="663cb-115">Dot field</span></span>

<span data-ttu-id="663cb-116">Representa el carácter de fin completo ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="663cb-116">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="663cb-117">Campo de endcom</span><span class="sxs-lookup"><span data-stu-id="663cb-117">EndComment field</span></span>

<span data-ttu-id="663cb-118">Representa el carácter que especifica el final de un comentario.</span><span class="sxs-lookup"><span data-stu-id="663cb-118">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="663cb-119">Campo LF</span><span class="sxs-lookup"><span data-stu-id="663cb-119">LF field</span></span>

<span data-ttu-id="663cb-120">Representa el carácter de avance de línea.</span><span class="sxs-lookup"><span data-stu-id="663cb-120">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="663cb-121">Campo de espacio</span><span class="sxs-lookup"><span data-stu-id="663cb-121">Space field</span></span>

<span data-ttu-id="663cb-122">Representa el carácter de espacio.</span><span class="sxs-lookup"><span data-stu-id="663cb-122">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="663cb-123">Campo StartComment</span><span class="sxs-lookup"><span data-stu-id="663cb-123">StartComment field</span></span>

<span data-ttu-id="663cb-124">Representa el carácter que especifica el inicio de un comentario.</span><span class="sxs-lookup"><span data-stu-id="663cb-124">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="663cb-125">Campo de pestaña</span><span class="sxs-lookup"><span data-stu-id="663cb-125">Tab field</span></span>

<span data-ttu-id="663cb-126">Representa el carácter de tabulación.</span><span class="sxs-lookup"><span data-stu-id="663cb-126">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="663cb-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="663cb-127">Requirements</span></span>

<span data-ttu-id="663cb-128">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="663cb-128">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="663cb-129">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="663cb-129">**Assembly:** System (in System.dll)</span></span>
