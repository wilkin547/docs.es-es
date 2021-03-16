---
title: 'Cambio importante: Las rutas de acceso al código UTF-7 están obsoletas'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde los constructores UTF7 y UTF7Encoding están obsoletos.
ms.date: 11/01/2020
ms.openlocfilehash: 7a0ba771e0fac2908ca37f16afb10118e1537161
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256990"
---
# <a name="utf-7-code-paths-are-obsolete"></a><span data-ttu-id="b3d8d-103">Las rutas de acceso al código UTF-7 están obsoletas</span><span class="sxs-lookup"><span data-stu-id="b3d8d-103">UTF-7 code paths are obsolete</span></span>

<span data-ttu-id="b3d8d-104">La codificación UTF-7 ya no se usa de forma generalizada en la mayoría de las aplicaciones, y muchas especificaciones ahora [prohíben su uso](https://security.stackexchange.com/a/68609/3573) en el intercambio.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-104">The UTF-7 encoding is no longer in wide use among applications, and many specs now [forbid its use](https://security.stackexchange.com/a/68609/3573) in interchange.</span></span> <span data-ttu-id="b3d8d-105">En ocasiones, también se [usa como vector de ataque](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) en aplicaciones que no anticipan el encuentro de datos codificados en UTF-7.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-105">It's also occasionally [used as an attack vector](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=utf-7) in applications that don't anticipate encountering UTF-7-encoded data.</span></span> <span data-ttu-id="b3d8d-106">Microsoft advierte contra el uso de <xref:System.Text.UTF7Encoding?displayProperty=nameWithType>, porque no proporciona detección de errores.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-106">Microsoft warns against use of <xref:System.Text.UTF7Encoding?displayProperty=nameWithType> because it doesn't provide error detection.</span></span>

<span data-ttu-id="b3d8d-107">Por consiguiente, la propiedad <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> y los constructores de <xref:System.Text.UTF7Encoding.%23ctor%2A> ahora están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-107">Consequently, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are now obsolete.</span></span> <span data-ttu-id="b3d8d-108">Además, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> y <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> ya no le permiten especificar `UTF-7`.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-108">Additionally, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> and <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType> no longer allow you to specify `UTF-7`.</span></span>

## <a name="change-description"></a><span data-ttu-id="b3d8d-109">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b3d8d-109">Change description</span></span>

<span data-ttu-id="b3d8d-110">Anteriormente, podía crear una instancia de la codificación UTF-7 mediante las API de <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-110">Previously, you could create an instance of the UTF-7 encoding by using the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> APIs.</span></span> <span data-ttu-id="b3d8d-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-111">For example:</span></span>

```csharp
Encoding enc1 = Encoding.GetEncoding("utf-7"); // By name.
Encoding enc2 = Encoding.GetEncoding(65000); // By code page.
```

<span data-ttu-id="b3d8d-112">Además, el método <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> enumera una instancia que representa la codificación UTF-7, que muestra todas las instancias de <xref:System.Text.Encoding> registradas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-112">Additionally, an instance that represents the UTF-7 encoding was enumerated by the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method, which enumerates all the <xref:System.Text.Encoding> instances registered on the system.</span></span>

<span data-ttu-id="b3d8d-113">A partir de .NET 5, la propiedad <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> y los constructores <xref:System.Text.UTF7Encoding.%23ctor%2A> están obsoletos y producen la advertencia `SYSLIB0001` (o `MSLIB0001` en versiones preliminares).</span><span class="sxs-lookup"><span data-stu-id="b3d8d-113">Starting in .NET 5, the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> property and <xref:System.Text.UTF7Encoding.%23ctor%2A> constructors are obsolete and produce warning `SYSLIB0001` (or `MSLIB0001` in preview versions).</span></span> <span data-ttu-id="b3d8d-114">Sin embargo, para reducir el número de advertencias que reciben los autores de la llamada cuando se usa la clase <xref:System.Text.UTF7Encoding>, el propio tipo <xref:System.Text.UTF7Encoding> no se marca como obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-114">However, to reduce the number of warnings that callers receive when using the <xref:System.Text.UTF7Encoding> class, the <xref:System.Text.UTF7Encoding> type itself is not marked obsolete.</span></span>

```csharp
// The next line generates warning SYSLIB0001.
UTF7Encoding enc = new UTF7Encoding();
// The next line does not generate a warning.
byte[] bytes = enc.GetBytes("Hello world!");
```

<span data-ttu-id="b3d8d-115">Además, los métodos <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> tratan el nombre de la codificación `utf-7` y la página de códigos `65000` como `unknown`.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-115">Additionally, the <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> methods treat the encoding name `utf-7` and the code page `65000` as `unknown`.</span></span> <span data-ttu-id="b3d8d-116">Cuando esto sucede, el método inicia una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-116">Treating the encoding as `unknown` causes the method to throw an <xref:System.ArgumentException>.</span></span>

```csharp
// Throws ArgumentException, same as calling Encoding.GetEncoding("unknown").
Encoding enc = Encoding.GetEncoding("utf-7");
```

<span data-ttu-id="b3d8d-117">Por último, el método <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> no incluye la codificación UTF-7 en la matriz <xref:System.Text.EncodingInfo> que devuelve.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-117">Finally, the <xref:System.Text.Encoding.GetEncodings?displayProperty=nameWithType> method doesn't include the UTF-7 encoding in the <xref:System.Text.EncodingInfo> array that it returns.</span></span> <span data-ttu-id="b3d8d-118">La codificación se excluye porque no se puede crear una instancia de ella.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-118">The encoding is excluded because it cannot be instantiated.</span></span>

```csharp
foreach (EncodingInfo encInfo in Encoding.GetEncodings())
{
    // The next line would throw if GetEncodings included UTF-7.
    Encoding enc = Encoding.GetEncoding(encInfo.Name);
}
```

## <a name="reason-for-change"></a><span data-ttu-id="b3d8d-119">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b3d8d-119">Reason for change</span></span>

<span data-ttu-id="b3d8d-120">Muchas aplicaciones llaman a `Encoding.GetEncoding("encoding-name")` con un valor de nombre de codificación proporcionado por un origen que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-120">Many applications call `Encoding.GetEncoding("encoding-name")` with an encoding name value that's provided by an untrusted source.</span></span> <span data-ttu-id="b3d8d-121">Por ejemplo, un cliente o un servidor web podrían tomar la parte `charset` del encabezado `Content-Type` y pasar el valor directamente a `Encoding.GetEncoding` sin validarlo.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-121">For example, a web client or server might take the `charset` portion of the `Content-Type` header and pass the value directly to `Encoding.GetEncoding` without validating it.</span></span> <span data-ttu-id="b3d8d-122">Como consecuencia, un punto de conexión malintencionado podría especificar `Content-Type: ...; charset=utf-7`, lo que provocaría un error de comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-122">This could allow a malicious endpoint to specify `Content-Type: ...; charset=utf-7`, which could cause the receiving application to misbehave.</span></span>

<span data-ttu-id="b3d8d-123">Además, la deshabilitación de las rutas de acceso al código UTF-7 permite optimizar los compiladores, como los que usa Blazor, para quitar completamente estas rutas de acceso al código de la aplicación resultante.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-123">Additionally, disabling UTF-7 code paths allows optimizing compilers, such as those used by Blazor, to remove these code paths entirely from the resulting application.</span></span> <span data-ttu-id="b3d8d-124">Como resultado, las aplicaciones compiladas se ejecutan de forma más eficaz y ocupan menos espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-124">As a result, the compiled applications run more efficiently and take less disk space.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b3d8d-125">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b3d8d-125">Version introduced</span></span>

<span data-ttu-id="b3d8d-126">5.0</span><span class="sxs-lookup"><span data-stu-id="b3d8d-126">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b3d8d-127">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b3d8d-127">Recommended action</span></span>

<span data-ttu-id="b3d8d-128">En la mayoría de los casos, no tiene que realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-128">In most cases, you don't need to take any action.</span></span> <span data-ttu-id="b3d8d-129">Sin embargo, en el caso de las aplicaciones que han activado previamente rutas de acceso al código relacionadas con UTF-7, tenga en cuenta las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-129">However, for apps that have previously activated UTF-7-related code paths, consider the guidance that follows.</span></span>

- <span data-ttu-id="b3d8d-130">Si la aplicación llama a <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> con nombres de codificación desconocidos proporcionados por un origen que no es de confianza:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-130">If your app calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> with unknown encoding names provided by an untrusted source:</span></span>

  <span data-ttu-id="b3d8d-131">Compare mejor los nombres de codificación con una lista de permitidos configurable.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-131">Instead, compare the encoding names against a configurable allow list.</span></span> <span data-ttu-id="b3d8d-132">La lista de permitidos configurable debe incluir, como mínimo, el estándar del sector "UTF-8".</span><span class="sxs-lookup"><span data-stu-id="b3d8d-132">The configurable allow list should at minimum include the industry-standard "utf-8".</span></span> <span data-ttu-id="b3d8d-133">En función de los clientes y los requisitos normativos, es posible que también deba permitir codificaciones específicas de la región, como "GB18030".</span><span class="sxs-lookup"><span data-stu-id="b3d8d-133">Depending on your clients and regulatory requirements, you may also need to allow region-specific encodings, such as "GB18030".</span></span>

  <span data-ttu-id="b3d8d-134">Si no implementa una lista de permitidos, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> devolverá cualquier <xref:System.Text.Encoding> que esté integrado en el sistema o que esté registrada a través de un objeto <xref:System.Text.EncodingProvider> personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-134">If you don't implement an allow list, <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType> will return any <xref:System.Text.Encoding> that's built into the system or that's registered via a custom <xref:System.Text.EncodingProvider>.</span></span> <span data-ttu-id="b3d8d-135">Audite los requisitos del servicio para validar que este es el comportamiento deseado.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-135">Audit your service's requirements to validate that this is the desired behavior.</span></span> <span data-ttu-id="b3d8d-136">UTF-7 sigue deshabilitado de forma predeterminada, a menos que la aplicación vuelva a habilitar el modificador de compatibilidad mencionado más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-136">UTF-7 continues to be disabled by default unless your application re-enables the compatibility switch mentioned later in this article.</span></span>

- <span data-ttu-id="b3d8d-137">Si usa <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> o <xref:System.Text.UTF7Encoding> en su propio protocolo o formato de archivo:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-137">If you're using <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding> within your own protocol or file format:</span></span>

  <span data-ttu-id="b3d8d-138">Cambie al uso de <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> o <xref:System.Text.UTF8Encoding>.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-138">Switch to using <xref:System.Text.Encoding.UTF8?displayProperty=nameWithType> or <xref:System.Text.UTF8Encoding>.</span></span> <span data-ttu-id="b3d8d-139">UTF-8 es un estándar del sector y es compatible con numerosos lenguajes, sistemas operativos y entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-139">UTF-8 is an industry standard and is widely supported across languages, operating systems, and runtimes.</span></span> <span data-ttu-id="b3d8d-140">El uso de UTF-8 facilita el mantenimiento futuro del código y hace que sea más interoperable con el resto del ecosistema.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-140">Using UTF-8 eases future maintenance of your code and makes it more interoperable with the rest of the ecosystem.</span></span>

- <span data-ttu-id="b3d8d-141">Si va a comparar una instancia de <xref:System.Text.Encoding> con <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-141">If you're comparing an <xref:System.Text.Encoding> instance against <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType>:</span></span>

  <span data-ttu-id="b3d8d-142">Considere mejor la posibilidad de realizar una comprobación con la página de códigos UTF-7 conocidos, que es `65000`.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-142">Instead, consider performing a check against the well-known UTF-7 code page, which is `65000`.</span></span> <span data-ttu-id="b3d8d-143">De esta manera, evita la advertencia y también se controlan algunos casos extremos, como, por ejemplo, si alguien llamó a `new UTF7Encoding()` o incluyó el tipo en una subclase.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-143">By comparing against the code page, you avoid the warning and also handle some edge cases, such as if somebody called `new UTF7Encoding()` or subclassed the type.</span></span>

  ```csharp
  void DoSomething(Encoding enc)
  {
      // Don't perform the check this way.
      // It produces a warning and misses some edge cases.
      if (enc == Encoding.UTF7)
      {
          // Encoding is UTF-7.
      }

      // Instead, perform the check this way.
      if (enc != null && enc.CodePage == 65000)
      {
          // Encoding is UTF-7.
      }
  }
  ```

- <span data-ttu-id="b3d8d-144">Debe usar <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> o <xref:System.Text.UTF7Encoding>:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-144">If you must use <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> or <xref:System.Text.UTF7Encoding>:</span></span>

  <span data-ttu-id="b3d8d-145">Puede suprimir la advertencia `SYSLIB0001` en el código o en el archivo *.csproj* del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-145">You can suppress the `SYSLIB0001` warning in code or within your project's *.csproj* file.</span></span>

  ```csharp
  #pragma warning disable SYSLIB0001 // Disable the warning.
  Encoding enc = Encoding.UTF7;
  #pragma warning restore SYSLIB0001 // Re-enable the warning.
  ```

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  > [!NOTE]
  > <span data-ttu-id="b3d8d-146">La supresión de `SYSLIB0001` solo deshabilita las advertencias <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> y <xref:System.Text.UTF7Encoding> de elementos obsoletos.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-146">Suppressing `SYSLIB0001` only disables the <xref:System.Text.Encoding.UTF7?displayProperty=nameWithType> and <xref:System.Text.UTF7Encoding> obsoletion warnings.</span></span> <span data-ttu-id="b3d8d-147">No deshabilita ninguna otra advertencia ni cambia el comportamiento de API como <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-147">It doesn't disable any other warnings or change the behavior of APIs like <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="b3d8d-148">Si se necesita la compatibilidad con `Encoding.GetEncoding("utf-7", ...)`:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-148">If you must support `Encoding.GetEncoding("utf-7", ...)`:</span></span>

  <span data-ttu-id="b3d8d-149">Puede volver a habilitarla mediante un modificador de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-149">You can re-enable support for this via a compatibility switch.</span></span> <span data-ttu-id="b3d8d-150">Este modificador de compatibilidad se puede especificar en el archivo *. csproj* de la aplicación o en un [archivo de configuración en tiempo de ejecución](../../../run-time-config/index.md), como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-150">This compatibility switch can be specified in the application's *.csproj* file or in a [run-time configuration file](../../../run-time-config/index.md), as shown in the following examples.</span></span>

  <span data-ttu-id="b3d8d-151">En el archivo *.csproj* de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-151">In the application's *.csproj* file:</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- Re-enable support for UTF-7 -->
     <EnableUnsafeUTF7Encoding>true</EnableUnsafeUTF7Encoding>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="b3d8d-152">En el archivo *runtimeConfig.template.json* de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b3d8d-152">In the application's *runtimeconfig.template.json* file:</span></span>

  ```json
  {
    "configProperties": {
      "System.Text.Encoding.EnableUnsafeUTF7Encoding": true
    }
  }
  ```

  > [!TIP]
  > <span data-ttu-id="b3d8d-153">Si vuelve a habilitar la compatibilidad con UTF-7, debe realizar una revisión de seguridad del código que llama a <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3d8d-153">If you re-enable support for UTF-7, you should perform a security review of code that calls <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b3d8d-154">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b3d8d-154">Affected APIs</span></span>

- <xref:System.Text.Encoding.UTF7?displayProperty=fullName>
- <xref:System.Text.UTF7Encoding.%23ctor>
- <xref:System.Text.UTF7Encoding.%23ctor(System.Boolean)>
- <xref:System.Text.Encoding.GetEncoding(System.Int32)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)?displayProperty=fullName>
- <xref:System.Text.Encoding.GetEncodings?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- Security

### Affected APIs

- `System.Text.Encoding.UTF7`
- `System.Text.UTF7Encoding.#ctor`
- `System.Text.UTF7Encoding.#ctor(System.Boolean)`
- `System.Text.Encoding.GetEncoding(System.Int32)`
- `System.Text.Encoding.GetEncoding(System.String)`
- `System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)`
- `System.Text.Encoding.GetEncodings`

-->
