---
title: 'Cambio importante: BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones'
description: Obtenga información sobre el cambio importante en .NET 5, donde BinaryFormatter.Deserialize vuelve a encapsular algunos objetos de excepción dentro de SerializationException.
ms.date: 08/18/2020
ms.openlocfilehash: 8e357035908f34c6c5c77d2a0728ab213bdc791a
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256353"
---
# <a name="binaryformatterdeserialize-rewraps-some-exceptions-in-serializationexception"></a><span data-ttu-id="ca03c-103">BinaryFormatter.Deserialize vuelve a encapsular algunas excepciones en SerializationException</span><span class="sxs-lookup"><span data-stu-id="ca03c-103">BinaryFormatter.Deserialize rewraps some exceptions in SerializationException</span></span>

<span data-ttu-id="ca03c-104">El método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> ahora vuelve a encapsular algunos objetos de excepción dentro de una excepción <xref:System.Runtime.Serialization.SerializationException> antes de propagarla de vuelta al auto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca03c-104">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method now rewraps some exception objects inside a <xref:System.Runtime.Serialization.SerializationException> before propagating the exception back to the caller.</span></span>

## <a name="change-description"></a><span data-ttu-id="ca03c-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ca03c-105">Change description</span></span>

<span data-ttu-id="ca03c-106">Anteriormente, el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> permitía que algunas excepciones arbitrarias, como <xref:System.ArgumentNullException>, se propagaran arriba de la pila a sus autores de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca03c-106">Previously, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method allowed some arbitrary exceptions, such as <xref:System.ArgumentNullException>, to propagate up the stack to its callers.</span></span>

<span data-ttu-id="ca03c-107">En .NET 5 y versiones posteriores, el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> detecta de forma más agresiva las excepciones que se producen debido a operaciones de deserialización no válidas y las encapsula en una excepción <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="ca03c-107">In .NET 5 and later, the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> method more aggressively catches exceptions that occur due to invalid deserialization operations and wraps them in a <xref:System.Runtime.Serialization.SerializationException>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ca03c-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ca03c-108">Version introduced</span></span>

<span data-ttu-id="ca03c-109">5.0</span><span class="sxs-lookup"><span data-stu-id="ca03c-109">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ca03c-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ca03c-110">Recommended action</span></span>

<span data-ttu-id="ca03c-111">En la mayoría de los casos, no tiene que realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="ca03c-111">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="ca03c-112">Sin embargo, si el sitio de llamada depende de que se inicie una excepción determinada, puede desencapsular la excepción de la excepción <xref:System.Runtime.Serialization.SerializationException> externa, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ca03c-112">However, if your call site depends on a particular exception being thrown, you can unwrap the exception from the outer <xref:System.Runtime.Serialization.SerializationException>, as shown in the following example.</span></span>

```csharp
Stream inputStream = GetInputStream();
var formatter = new BinaryFormatter();

try
{
    object deserialized = formatter.Deserialize(inputStream);
}
catch (MyException myEx)
{
    // Handle 'myEx' here in case it was thrown directly.
}
catch (SerializationException serEx) when (serEx.InnerException is MyException myEx)
{
    // Handle 'myEx' here in case it was wrapped in SerializationException.
}
```

## <a name="affected-apis"></a><span data-ttu-id="ca03c-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ca03c-113">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`

### Category

Serialization

-->
