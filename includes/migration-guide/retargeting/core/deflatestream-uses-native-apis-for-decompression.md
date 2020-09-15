---
ms.openlocfilehash: 7e42a294b151d07a6fdc61308cdf92df7a31a1d6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614725"
---
### <a name="deflatestream-uses-native-apis-for-decompression"></a><span data-ttu-id="1fd99-101">DeflateStream usa las API nativas para la descompresión</span><span class="sxs-lookup"><span data-stu-id="1fd99-101">DeflateStream uses native APIs for decompression</span></span>

#### <a name="details"></a><span data-ttu-id="1fd99-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1fd99-102">Details</span></span>

<span data-ttu-id="1fd99-103">A partir de .NET Framework 4.7.2, la implementación de la descompresión en la clase `T:System.IO.Compression.DeflateStream` ha cambiado para usar las API nativas de Windows de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1fd99-103">Starting with the .NET Framework 4.7.2, the implementation of decompression in the `T:System.IO.Compression.DeflateStream` class has changed to use native Windows APIs by default.</span></span> <span data-ttu-id="1fd99-104">Normalmente, esto da como resultado una mejora considerable del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1fd99-104">Typically, this results in a substantial performance improvement.</span></span> <span data-ttu-id="1fd99-105">En todas las aplicaciones de .NET que tienen como destino la versión 4.7.2 de .NET Framework o una versión posterior se usa la implementación nativa. Es posible que este cambio provoque algunas diferencias de comportamiento, como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1fd99-105">All .NET applications targeting the .NET Framework version 4.7.2 or higher use the native implementation.This change might result in some differences in behavior, which include:</span></span>

- <span data-ttu-id="1fd99-106">Los mensajes de excepción pueden ser diferentes.</span><span class="sxs-lookup"><span data-stu-id="1fd99-106">Exception messages may be different.</span></span> <span data-ttu-id="1fd99-107">Pero el tipo de excepción que se inicia sigue siendo el mismo.</span><span class="sxs-lookup"><span data-stu-id="1fd99-107">However, the type of exception thrown remains the same.</span></span>
- <span data-ttu-id="1fd99-108">Algunas situaciones especiales, por ejemplo no tener memoria suficiente para completar una operación, se pueden administrar de otra manera.</span><span class="sxs-lookup"><span data-stu-id="1fd99-108">Some special situations, such as not having enough memory to complete an operation, may be handled differently.</span></span>
- <span data-ttu-id="1fd99-109">Hay diferencias conocidas para el análisis del encabezado de gzip (Nota: Solo se ve afectado `GZipStream` establecido para la descompresión):</span><span class="sxs-lookup"><span data-stu-id="1fd99-109">There are known differences for parsing gzip header (note: only `GZipStream` set for decompression is affected):</span></span>
- <span data-ttu-id="1fd99-110">Se pueden iniciar excepciones al analizar encabezados no válidos en momentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="1fd99-110">Exceptions when parsing invalid headers may be thrown at different times.</span></span>
- <span data-ttu-id="1fd99-111">La implementación nativa exige que los valores para algunas marcas reservadas dentro del encabezado de gzip (es decir, [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) se establezcan según la especificación, lo que puede provocar que se inicie una excepción donde anteriormente se ignoraban los valores no válidos.</span><span class="sxs-lookup"><span data-stu-id="1fd99-111">The native implementation enforces that values for some reserved flags inside the gzip header (i.e. [FLG](http://www.zlib.org/rfc-gzip.html#header-trailer)) are set according to the specification, which may cause it to throw an exception where previously invalid values were ignored.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1fd99-112">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1fd99-112">Suggestion</span></span>

<span data-ttu-id="1fd99-113">Si la descompresión con las API nativas ha afectado negativamente el comportamiento de la aplicación, puede descartar esta característica si agrega el modificador `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` a la sección `runtime` del archivo app.config y lo establece en `true`:</span><span class="sxs-lookup"><span data-stu-id="1fd99-113">If decompression with native APIs has adversely affected the behavior of your app, you can opt out of this feature by adding the `Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression` switch to the `runtime` section of your app.config file and setting it to `true`:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="1fd99-114">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="1fd99-114">Name</span></span>    | <span data-ttu-id="1fd99-115">Valor</span><span class="sxs-lookup"><span data-stu-id="1fd99-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1fd99-116">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1fd99-116">Scope</span></span>   | <span data-ttu-id="1fd99-117">Secundaria</span><span class="sxs-lookup"><span data-stu-id="1fd99-117">Minor</span></span>       |
| <span data-ttu-id="1fd99-118">Versión</span><span class="sxs-lookup"><span data-stu-id="1fd99-118">Version</span></span> | <span data-ttu-id="1fd99-119">4.7.2</span><span class="sxs-lookup"><span data-stu-id="1fd99-119">4.7.2</span></span>       |
| <span data-ttu-id="1fd99-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="1fd99-120">Type</span></span>    | <span data-ttu-id="1fd99-121">Redestinación</span><span class="sxs-lookup"><span data-stu-id="1fd99-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1fd99-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1fd99-122">Affected APIs</span></span>

- <xref:System.IO.Compression.DeflateStream?displayProperty=nameWithType>
- <xref:System.IO.Compression.GZipStream?displayProperty=nameWithType>
