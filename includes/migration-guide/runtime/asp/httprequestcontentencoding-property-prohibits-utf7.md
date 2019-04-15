---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235798"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="0e2e5-101">La propiedad HttpRequest.ContentEncoding prohíbe la codificación UTF7</span><span class="sxs-lookup"><span data-stu-id="0e2e5-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0e2e5-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0e2e5-102">Details</span></span>|<span data-ttu-id="0e2e5-103">A partir de .NET Framework 4.5, la codificación UTF-7 está prohibida en los cuerpos de elementos <xref:System.Web.HttpRequest?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="0e2e5-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="0e2e5-104">Los datos de las aplicaciones que dependen de los datos de entrada UTF-7 no se descodificarán correctamente en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="0e2e5-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="0e2e5-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0e2e5-105">Suggestion</span></span>|<span data-ttu-id="0e2e5-106">Lo ideal sería actualizar las aplicaciones para que no usen la codificación UTF-7 en los elementos <xref:System.Web.HttpRequest?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="0e2e5-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="0e2e5-107">También es posible restaurar el comportamiento heredado usando el atributo <code>aspnet:AllowUtf7RequestContentEncoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0e2e5-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="0e2e5-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0e2e5-108">Scope</span></span>|<span data-ttu-id="0e2e5-109">Borde</span><span class="sxs-lookup"><span data-stu-id="0e2e5-109">Edge</span></span>|
|<span data-ttu-id="0e2e5-110">Versión</span><span class="sxs-lookup"><span data-stu-id="0e2e5-110">Version</span></span>|<span data-ttu-id="0e2e5-111">4.5</span><span class="sxs-lookup"><span data-stu-id="0e2e5-111">4.5</span></span>|
|<span data-ttu-id="0e2e5-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="0e2e5-112">Type</span></span>|<span data-ttu-id="0e2e5-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0e2e5-113">Runtime</span></span>|
|<span data-ttu-id="0e2e5-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0e2e5-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
