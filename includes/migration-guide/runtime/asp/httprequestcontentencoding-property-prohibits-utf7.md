---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497768"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="70259-101">La propiedad HttpRequest.ContentEncoding prohíbe la codificación UTF7</span><span class="sxs-lookup"><span data-stu-id="70259-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="70259-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="70259-102">Details</span></span>

<span data-ttu-id="70259-103">A partir de .NET Framework 4.5, la codificación UTF-7 está prohibida en los cuerpos de elementos <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="70259-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="70259-104">Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="70259-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="70259-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="70259-105">Suggestion</span></span>

<span data-ttu-id="70259-106">Lo ideal sería actualizar las aplicaciones para que no usen la codificación UTF-7 en los elementos <xref:System.Web.HttpRequest?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="70259-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="70259-107">También es posible restaurar el comportamiento heredado usando el atributo <code>aspnet:AllowUtf7RequestContentEncoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="70259-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="70259-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="70259-108">Name</span></span>    | <span data-ttu-id="70259-109">Valor</span><span class="sxs-lookup"><span data-stu-id="70259-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="70259-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="70259-110">Scope</span></span>   |<span data-ttu-id="70259-111">Borde</span><span class="sxs-lookup"><span data-stu-id="70259-111">Edge</span></span>|
|<span data-ttu-id="70259-112">Versión</span><span class="sxs-lookup"><span data-stu-id="70259-112">Version</span></span>|<span data-ttu-id="70259-113">4.5</span><span class="sxs-lookup"><span data-stu-id="70259-113">4.5</span></span>|
|<span data-ttu-id="70259-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="70259-114">Type</span></span>|<span data-ttu-id="70259-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="70259-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="70259-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="70259-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
