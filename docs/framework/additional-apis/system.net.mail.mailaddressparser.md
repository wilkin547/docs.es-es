---
description: 'Más información sobre: clase MailAddressParser'
title: Clase MailAddressParser (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Mail.MailAddressParser
- System.Net.Mail.MailAddressParser.ParseAddress
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 5ad534e731e283f5449b3b8cc8e87628716da9b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699771"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="537b9-103">Clase MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="537b9-103">MailAddressParser class</span></span>

<span data-ttu-id="537b9-104">Analiza las direcciones de correo electrónico como se describe en RFC 2822.</span><span class="sxs-lookup"><span data-stu-id="537b9-104">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="537b9-105">Esta clase no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="537b9-105">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="537b9-106">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="537b9-106">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="537b9-107">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="537b9-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="537b9-108">Método ParseAddress</span><span class="sxs-lookup"><span data-stu-id="537b9-108">ParseAddress method</span></span>

<span data-ttu-id="537b9-109">Analiza una única dirección de correo electrónico de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="537b9-109">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="537b9-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="537b9-110">Parameters</span></span>

<span data-ttu-id="537b9-111">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="537b9-111">`data` <xref:System.String></span></span>

<span data-ttu-id="537b9-112">Cadena que contiene una dirección de correo electrónico que se va a analizar.</span><span class="sxs-lookup"><span data-stu-id="537b9-112">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="537b9-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="537b9-113">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="537b9-114">Una dirección de correo electrónico válida.</span><span class="sxs-lookup"><span data-stu-id="537b9-114">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="537b9-115">Excepciones</span><span class="sxs-lookup"><span data-stu-id="537b9-115">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="537b9-116">La dirección de correo electrónico no es válida.</span><span class="sxs-lookup"><span data-stu-id="537b9-116">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="537b9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="537b9-117">Requirements</span></span>

<span data-ttu-id="537b9-118">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="537b9-118">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="537b9-119">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="537b9-119">**Assembly:** System (in System.dll)</span></span>
