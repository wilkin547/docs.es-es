---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497897"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="49bfd-101">ValidationContext.MemberName de APS.NET no es NULL cuando se usa DataAnnotations.ValidationAttribute personalizado</span><span class="sxs-lookup"><span data-stu-id="49bfd-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

#### <a name="details"></a><span data-ttu-id="49bfd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="49bfd-102">Details</span></span>

<span data-ttu-id="49bfd-103">En .NET Framework 4.7.2 y versiones anteriores, cuando se usa <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> personalizado, la propiedad <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="49bfd-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns `null`.</span></span> <span data-ttu-id="49bfd-104">En .NET Framework, versión 4.8, anterior a la actualización de octubre de 2019, devuelve el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="49bfd-104">In .NET Framework 4.8 version prior to the October 2019 update, it returns the member name.</span></span> <span data-ttu-id="49bfd-105">A partir de la [versión preliminar de .NET Framework de octubre de 2019 del paquete acumulativo de actualizaciones de calidad](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) para .NET Framework 4.8, devuelve `null` de forma predeterminada, pero puede optar por devolver el nombre del miembro en su lugar.</span><span class="sxs-lookup"><span data-stu-id="49bfd-105">Starting with [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8, it returns `null` by default, but you can opt in to return the member name instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="49bfd-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="49bfd-106">Suggestion</span></span>

<span data-ttu-id="49bfd-107">Agregue la siguiente configuración a su archivo *web.config* para que la propiedad devuelva el nombre de miembro en la [versión preliminar de .NET Framework de octubre de 2019 del paquete acumulativo de actualizaciones de calidad](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) para .NET Framework 4.8 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="49bfd-107">Add the following setting to your *web.config* file for the property to return the member name in [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8 and later versions:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="49bfd-108">En .NET Framework, versión 4.8, anterior a la actualización de octubre de 2019, al agregarlo al archivo *web.config* se restaura el comportamiento anterior y la propiedad devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="49bfd-108">In .NET Framework 4.8 version prior to the October 2019 update,  adding this to your *web.config* file restores the previous behavior and the property returns `null`.</span></span>

| <span data-ttu-id="49bfd-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="49bfd-109">Name</span></span>    | <span data-ttu-id="49bfd-110">Valor</span><span class="sxs-lookup"><span data-stu-id="49bfd-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="49bfd-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="49bfd-111">Scope</span></span>   |<span data-ttu-id="49bfd-112">Desconocido</span><span class="sxs-lookup"><span data-stu-id="49bfd-112">Unknown</span></span>|
|<span data-ttu-id="49bfd-113">Versión</span><span class="sxs-lookup"><span data-stu-id="49bfd-113">Version</span></span>|<span data-ttu-id="49bfd-114">4.8</span><span class="sxs-lookup"><span data-stu-id="49bfd-114">4.8</span></span>|
|<span data-ttu-id="49bfd-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="49bfd-115">Type</span></span>|<span data-ttu-id="49bfd-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="49bfd-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="49bfd-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="49bfd-117">Affected APIs</span></span>

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
