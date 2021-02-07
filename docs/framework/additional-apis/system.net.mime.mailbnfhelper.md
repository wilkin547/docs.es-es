---
description: 'Más información sobre: clase MailBnfHelper'
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
ms.openlocfilehash: 942b5c423d2f63985a8f7840f69d956bbade7582
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699654"
---
# <a name="mailbnfhelper-class"></a><span data-ttu-id="8a693-103">Clase MailBnfHelper</span><span class="sxs-lookup"><span data-stu-id="8a693-103">MailBnfHelper class</span></span>

<span data-ttu-id="8a693-104">Contiene métodos de utilidad para analizar las cadenas con formato de mensajes de Internet.</span><span class="sxs-lookup"><span data-stu-id="8a693-104">Contains utility methods for parsing internet message-formatted strings.</span></span> <span data-ttu-id="8a693-105">Esta clase no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="8a693-105">This class cannot be inherited.</span></span>

```csharp
internal static class MailBnfHelper
```

> [!WARNING]
> <span data-ttu-id="8a693-106">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="8a693-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="8a693-107">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="8a693-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="ascii7bitmaxvalue-field"></a><span data-ttu-id="8a693-108">Campo Ascii7bitMaxValue</span><span class="sxs-lookup"><span data-stu-id="8a693-108">Ascii7bitMaxValue field</span></span>

<span data-ttu-id="8a693-109">Representa el valor ASCII máximo de 7 bits.</span><span class="sxs-lookup"><span data-stu-id="8a693-109">Represents the maximum 7-bit Ascii value.</span></span>

```csharp
internal static readonly int Ascii7bitMaxValue
```

## <a name="atext-field"></a><span data-ttu-id="8a693-110">Campo texto</span><span class="sxs-lookup"><span data-stu-id="8a693-110">Atext field</span></span>

<span data-ttu-id="8a693-111">Representa los caracteres permitidos en los átomos.</span><span class="sxs-lookup"><span data-stu-id="8a693-111">Represents the characters allowed in atoms.</span></span>

```csharp
internal static bool[] Atext
```

## <a name="cr-field"></a><span data-ttu-id="8a693-112">Campo CR</span><span class="sxs-lookup"><span data-stu-id="8a693-112">CR field</span></span>

<span data-ttu-id="8a693-113">Representa el carácter de retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="8a693-113">Represents the carriage-return character.</span></span>

```csharp
internal static readonly char CR
```

## <a name="ctext-field"></a><span data-ttu-id="8a693-114">Campo Ctext</span><span class="sxs-lookup"><span data-stu-id="8a693-114">Ctext field</span></span>

<span data-ttu-id="8a693-115">Representa los caracteres permitidos dentro de los comentarios.</span><span class="sxs-lookup"><span data-stu-id="8a693-115">Represents the characters allowed inside of comments.</span></span>

```csharp
internal static bool[] Ctext
```

## <a name="dot-field"></a><span data-ttu-id="8a693-116">Campo de punto</span><span class="sxs-lookup"><span data-stu-id="8a693-116">Dot field</span></span>

<span data-ttu-id="8a693-117">Representa el carácter de fin completo ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="8a693-117">Represents the full-stop character (`.`).</span></span>

```csharp
internal static readonly char Dot
```

## <a name="endcomment-field"></a><span data-ttu-id="8a693-118">Campo de endcom</span><span class="sxs-lookup"><span data-stu-id="8a693-118">EndComment field</span></span>

<span data-ttu-id="8a693-119">Representa el carácter que especifica el final de un comentario.</span><span class="sxs-lookup"><span data-stu-id="8a693-119">Represents the character that specifies the end of a comment.</span></span>

```csharp
internal static readonly char EndComment
```

## <a name="lf-field"></a><span data-ttu-id="8a693-120">Campo LF</span><span class="sxs-lookup"><span data-stu-id="8a693-120">LF field</span></span>

<span data-ttu-id="8a693-121">Representa el carácter de avance de línea.</span><span class="sxs-lookup"><span data-stu-id="8a693-121">Represents the line-feed character.</span></span>

```csharp
internal static readonly char LF
```

## <a name="space-field"></a><span data-ttu-id="8a693-122">Campo de espacio</span><span class="sxs-lookup"><span data-stu-id="8a693-122">Space field</span></span>

<span data-ttu-id="8a693-123">Representa el carácter de espacio.</span><span class="sxs-lookup"><span data-stu-id="8a693-123">Represents the space character.</span></span>

```csharp
internal static readonly char Space
```

## <a name="startcomment-field"></a><span data-ttu-id="8a693-124">Campo StartComment</span><span class="sxs-lookup"><span data-stu-id="8a693-124">StartComment field</span></span>

<span data-ttu-id="8a693-125">Representa el carácter que especifica el inicio de un comentario.</span><span class="sxs-lookup"><span data-stu-id="8a693-125">Represents the character that specifies the start of a comment.</span></span>

```csharp
internal static readonly char StartComment
```

## <a name="tab-field"></a><span data-ttu-id="8a693-126">Campo de pestaña</span><span class="sxs-lookup"><span data-stu-id="8a693-126">Tab field</span></span>

<span data-ttu-id="8a693-127">Representa el carácter de tabulación.</span><span class="sxs-lookup"><span data-stu-id="8a693-127">Represents the tab character.</span></span>

```csharp
internal static readonly char Tab
```

## <a name="requirements"></a><span data-ttu-id="8a693-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a693-128">Requirements</span></span>

<span data-ttu-id="8a693-129">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="8a693-129">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="8a693-130">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="8a693-130">**Assembly:** System (in System.dll)</span></span>
