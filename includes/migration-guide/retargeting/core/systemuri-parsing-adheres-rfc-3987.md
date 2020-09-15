---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617278"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a><span data-ttu-id="49fd4-101">El análisis de System.Uri cumple con las disposiciones de RFC 3987</span><span class="sxs-lookup"><span data-stu-id="49fd4-101">System.Uri parsing adheres to RFC 3987</span></span>

#### <a name="details"></a><span data-ttu-id="49fd4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="49fd4-102">Details</span></span>

<span data-ttu-id="49fd4-103">El análisis de URI se ha modificado de varias formas en .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="49fd4-103">URI parsing has changed in several ways in .NET Framework 4.5.</span></span> <span data-ttu-id="49fd4-104">Pero tenga en cuenta que estos cambios solo afectan al código que tenga como destino .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="49fd4-104">Note, however, that these changes only affect code targeting .NET Framework 4.5.</span></span> <span data-ttu-id="49fd4-105">Si un binario tiene como destino .NET Framework 4.0, se observará el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="49fd4-105">If a binary targets .NET Framework 4.0, the old behavior will be observed.</span></span> <span data-ttu-id="49fd4-106">Entre los cambios efectuados en el análisis de URI en .NET Framework 4.5 se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="49fd4-106">Changes to URI parsing in .NET Framework 4.5 include:</span></span>

- <span data-ttu-id="49fd4-107">Los análisis de identificadores URI efectuarán comprobaciones de normalización y caracteres conforme a las normas más recientes sobre IRI indicadas en RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="49fd4-107">URI parsing will perform normalization and character checking according to the latest IRI rules in RFC 3987.</span></span>
- <span data-ttu-id="49fd4-108">La forma de normalización C de Unicode solo se ejecutará en la sección de host del identificador URI.</span><span class="sxs-lookup"><span data-stu-id="49fd4-108">Unicode normalization form C will only be performed on the host portion of the URI.</span></span>
- <span data-ttu-id="49fd4-109">Mailto no válido: Los identificadores URI ahora generarán una excepción.</span><span class="sxs-lookup"><span data-stu-id="49fd4-109">Invalid mailto: URIs will now cause an exception.</span></span>
- <span data-ttu-id="49fd4-110">Ahora se conservan los puntos finales al final de un segmento de trazado.</span><span class="sxs-lookup"><span data-stu-id="49fd4-110">Trailing dots at the end of a path segment are now preserved.</span></span>
- <span data-ttu-id="49fd4-111">Los identificadores URI de `file://` no aplican secuencias de escape al carácter `?`.</span><span class="sxs-lookup"><span data-stu-id="49fd4-111">`file://` URIs do not escape the `?` character.</span></span>
- <span data-ttu-id="49fd4-112">Los caracteres de control Unicode `U+0080` a `U+009F` no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="49fd4-112">Unicode control characters `U+0080` through `U+009F` are not supported.</span></span>
- <span data-ttu-id="49fd4-113">Las secuencias de escape de los caracteres de coma `,` y `%2c` no se eliminan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="49fd4-113">Comma characters `,` or `%2c` are not automatically unescaped.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="49fd4-114">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="49fd4-114">Suggestion</span></span>

<span data-ttu-id="49fd4-115">Si es necesario usar la semántica de análisis de URI anterior de .NET Framework 4.0 (lo que no es habitual), se puede usar si se selecciona .NET Framework 4.0 como destino.</span><span class="sxs-lookup"><span data-stu-id="49fd4-115">If the old .NET Framework 4.0 URI parsing semantics are necessary (they often aren't), they can be used by targeting .NET Framework 4.0.</span></span> <span data-ttu-id="49fd4-116">Esto se puede hacer mediante un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> en el ensamblado, o bien a través de la interfaz de usuario del sistema del proyecto de Visual Studio, en la página "Propiedades del proyecto".</span><span class="sxs-lookup"><span data-stu-id="49fd4-116">This can be accomplished by using a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> on the assembly, or through Visual Studio's project system UI in the 'project properties' page.</span></span>

| <span data-ttu-id="49fd4-117">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="49fd4-117">Name</span></span>    | <span data-ttu-id="49fd4-118">Valor</span><span class="sxs-lookup"><span data-stu-id="49fd4-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="49fd4-119">Ámbito</span><span class="sxs-lookup"><span data-stu-id="49fd4-119">Scope</span></span>   | <span data-ttu-id="49fd4-120">Major</span><span class="sxs-lookup"><span data-stu-id="49fd4-120">Major</span></span>       |
| <span data-ttu-id="49fd4-121">Versión</span><span class="sxs-lookup"><span data-stu-id="49fd4-121">Version</span></span> | <span data-ttu-id="49fd4-122">4.5</span><span class="sxs-lookup"><span data-stu-id="49fd4-122">4.5</span></span>         |
| <span data-ttu-id="49fd4-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="49fd4-123">Type</span></span>    | <span data-ttu-id="49fd4-124">Redestinación</span><span class="sxs-lookup"><span data-stu-id="49fd4-124">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="49fd4-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="49fd4-125">Affected APIs</span></span>

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
