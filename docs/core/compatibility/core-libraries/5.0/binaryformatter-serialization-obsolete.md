---
title: 'Cambio importante: Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET por el que los métodos de serialización y deserialización de BinaryFormatter, Formatter e IFormatter están obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: 5807a7d4e6beab26b9848b803922396dd893075b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760187"
---
# <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a><span data-ttu-id="c7f83-103">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c7f83-103">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>

<span data-ttu-id="c7f83-104">Los métodos `Serialize` y `Deserialize` de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter> y <xref:System.Runtime.Serialization.IFormatter> ahora están obsoletos como advertencia.</span><span class="sxs-lookup"><span data-stu-id="c7f83-104">`Serialize` and `Deserialize` methods on <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, <xref:System.Runtime.Serialization.Formatter>, and <xref:System.Runtime.Serialization.IFormatter> are now obsolete as warning.</span></span> <span data-ttu-id="c7f83-105">Además, la serialización de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> está prohibida de forma predeterminada en aplicaciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c7f83-105">Additionally, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is prohibited by default for ASP.NET apps.</span></span>

## <a name="change-description"></a><span data-ttu-id="c7f83-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c7f83-106">Change description</span></span>

<span data-ttu-id="c7f83-107">Debido a [vulnerabilidades de seguridad](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) en <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, los siguientes métodos ahora están obsoletos y generan una advertencia en tiempo de compilación con el identificador `SYSLIB0011`.</span><span class="sxs-lookup"><span data-stu-id="c7f83-107">Due to [security vulnerabilities](../../../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following methods are now obsolete and produce a compile-time warning with ID `SYSLIB0011`.</span></span> <span data-ttu-id="c7f83-108">Además, en las aplicaciones ASP.NET Core 5.0 y versiones posteriores, iniciarán una excepción <xref:System.NotSupportedException>, a menos que la aplicación web haya vuelto a habilitar la funcionalidad <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="c7f83-108">Additionally, in ASP.NET Core 5.0 and later apps, they will throw a <xref:System.NotSupportedException>, unless the web app has re-enabled <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> functionality.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

<span data-ttu-id="c7f83-109">Los siguientes métodos de serialización también están obsoletos y generan una advertencia `SYSLIB0011`, pero no presentan cambios de comportamiento:</span><span class="sxs-lookup"><span data-stu-id="c7f83-109">The following serialization methods are also obsolete and produce warning `SYSLIB0011`, but have no behavioral changes:</span></span>

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="version-introduced"></a><span data-ttu-id="c7f83-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c7f83-110">Version introduced</span></span>

<span data-ttu-id="c7f83-111">5.0</span><span class="sxs-lookup"><span data-stu-id="c7f83-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c7f83-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c7f83-112">Reason for change</span></span>

<span data-ttu-id="c7f83-113">En un esfuerzo por poner fin al uso de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> dentro del ecosistema de .NET, estos métodos están marcados como obsoletos.</span><span class="sxs-lookup"><span data-stu-id="c7f83-113">These methods are marked obsolete as part of an effort to wind down usage of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> within the .NET ecosystem.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c7f83-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c7f83-114">Recommended action</span></span>

- <span data-ttu-id="c7f83-115">Deje de usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> en el código.</span><span class="sxs-lookup"><span data-stu-id="c7f83-115">Stop using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in your code.</span></span> <span data-ttu-id="c7f83-116">Considere mejor el uso de <xref:System.Text.Json.JsonSerializer> o <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c7f83-116">Instead, consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="c7f83-117">Para más información, consulte [Guía de seguridad de BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="c7f83-117">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

- <span data-ttu-id="c7f83-118">Puede suprimir temporalmente la advertencia en tiempo de compilación de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, que es `SYSLIB0011`.</span><span class="sxs-lookup"><span data-stu-id="c7f83-118">You can temporarily suppress the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> compile-time warning, which is `SYSLIB0011`.</span></span> <span data-ttu-id="c7f83-119">Le recomendamos que evalúe detenidamente el código para detectar los riesgos antes de elegir esta opción.</span><span class="sxs-lookup"><span data-stu-id="c7f83-119">We recommend that you thoroughly assess your code for risks before choosing this option.</span></span> <span data-ttu-id="c7f83-120">La manera más fácil de suprimir las advertencias es colocar directivas `#pragma` en torno al sitio de llamada individual.</span><span class="sxs-lookup"><span data-stu-id="c7f83-120">The easiest way to suppress the warnings is to surround the individual call site with `#pragma` directives.</span></span>

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  <span data-ttu-id="c7f83-121">También puede suprimir la advertencia en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c7f83-121">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  <span data-ttu-id="c7f83-122">Si suprime la advertencia en el archivo del proyecto, se suprime la advertencia para todos los archivos de código del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c7f83-122">If you suppress the warning in the project file, the warning is suppressed for all code files in the project.</span></span> <span data-ttu-id="c7f83-123">La supresión de `SYSLIB0011` no suprime las advertencias causadas por el uso de otras API obsoletas.</span><span class="sxs-lookup"><span data-stu-id="c7f83-123">Suppressing `SYSLIB0011` does not suppress warnings caused by using other obsolete APIs.</span></span>

- <span data-ttu-id="c7f83-124">Para seguir usando <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> en aplicaciones ASP.NET, puede volver a habilitarlo en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c7f83-124">To continue using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> in ASP.NET apps, you can re-enable it in the project file.</span></span> <span data-ttu-id="c7f83-125">Sin embargo, se recomienda encarecidamente no hacerlo.</span><span class="sxs-lookup"><span data-stu-id="c7f83-125">However, it's strongly recommended not to do this.</span></span> <span data-ttu-id="c7f83-126">Para más información, consulte [Guía de seguridad de BinaryFormatter](../../../../standard/serialization/binaryformatter-security-guide.md).</span><span class="sxs-lookup"><span data-stu-id="c7f83-126">For more information, see [BinaryFormatter security guide](../../../../standard/serialization/binaryformatter-security-guide.md).</span></span>

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

<span data-ttu-id="c7f83-127">Para más información sobre las acciones recomendadas, consulte [Resolución de errores de desactivación y deshabilitación de BinaryFormatter](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="c7f83-127">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c7f83-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c7f83-128">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET Core

### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
