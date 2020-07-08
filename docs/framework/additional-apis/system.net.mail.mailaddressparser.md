---
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
ms.openlocfilehash: ff83f6946539fa262ccde980052627f98c75601d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051355"
---
# <a name="mailaddressparser-class"></a><span data-ttu-id="0a1f0-102">Clase MailAddressParser</span><span class="sxs-lookup"><span data-stu-id="0a1f0-102">MailAddressParser class</span></span>

<span data-ttu-id="0a1f0-103">Analiza las direcciones de correo electrónico como se describe en RFC 2822.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-103">Parses email addresses as described in RFC 2822.</span></span> <span data-ttu-id="0a1f0-104">No se puede heredar esta clase.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-104">This class cannot be inherited.</span></span>

```csharp
internal static class MailAddressParser
```

> [!WARNING]
> <span data-ttu-id="0a1f0-105">Esta clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0a1f0-106">Microsoft no admite el uso de esta clase en una aplicación de producción en cualquier circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="parseaddress-method"></a><span data-ttu-id="0a1f0-107">Método ParseAddress</span><span class="sxs-lookup"><span data-stu-id="0a1f0-107">ParseAddress method</span></span>

<span data-ttu-id="0a1f0-108">Analiza una única dirección de correo electrónico de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-108">Parses a single email address from the specified string.</span></span>

```csharp
internal static MailAddress ParseAddress(string data)
```

### <a name="parameters"></a><span data-ttu-id="0a1f0-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a1f0-109">Parameters</span></span>

<span data-ttu-id="0a1f0-110">`data` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="0a1f0-110">`data` <xref:System.String></span></span>

<span data-ttu-id="0a1f0-111">Cadena que contiene una dirección de correo electrónico que se va a analizar.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-111">The string that contains an email address to be parsed.</span></span>

### <a name="return-value"></a><span data-ttu-id="0a1f0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0a1f0-112">Return value</span></span>

<xref:System.Net.Mail.MailAddress>

<span data-ttu-id="0a1f0-113">Una dirección de correo electrónico válida.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-113">A valid email address.</span></span>

### <a name="exceptions"></a><span data-ttu-id="0a1f0-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="0a1f0-114">Exceptions</span></span>

<xref:System.FormatException?displayProperty=nameWithType>

<span data-ttu-id="0a1f0-115">La dirección de correo electrónico no es válida.</span><span class="sxs-lookup"><span data-stu-id="0a1f0-115">The email address is invalid.</span></span>

## <a name="requirements"></a><span data-ttu-id="0a1f0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a1f0-116">Requirements</span></span>

<span data-ttu-id="0a1f0-117">**Espacio de nombres:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0a1f0-117">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0a1f0-118">**Ensamblado:** Sistema (en System.dll)</span><span class="sxs-lookup"><span data-stu-id="0a1f0-118">**Assembly:** System (in System.dll)</span></span>
