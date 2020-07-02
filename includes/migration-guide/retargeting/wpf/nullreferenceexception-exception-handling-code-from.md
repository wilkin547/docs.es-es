---
ms.openlocfilehash: 9c9c4ec55143ef991e9b69a389e0f3368263bb4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614844"
---
### <a name="nullreferenceexception-in-exception-handling-code-from-imagesourceconverterconvertfrom"></a><span data-ttu-id="1c127-101">Excepción NullReferenceException en el código de control de excepciones de ImageSourceConverter.ConvertFrom</span><span class="sxs-lookup"><span data-stu-id="1c127-101">NullReferenceException in exception handling code from ImageSourceConverter.ConvertFrom</span></span>

#### <a name="details"></a><span data-ttu-id="1c127-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1c127-102">Details</span></span>

<span data-ttu-id="1c127-103">Un error en el código de control de excepciones <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> ha hecho que se produjese una excepción <xref:System.NullReferenceException?displayProperty=fullName> incorrecta en lugar de la excepción prevista (<xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> o <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="1c127-103">An error in the exception handling code for <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)> caused an incorrect <xref:System.NullReferenceException?displayProperty=fullName> to be thrown instead of the intended exception ( <xref:System.IO.DirectoryNotFoundException?displayProperty=fullName> or <xref:System.IO.FileNotFoundException?displayProperty=fullName>).</span></span> <span data-ttu-id="1c127-104">Este cambio corrige el error para que el método produzca la excepción correcta.</span><span class="sxs-lookup"><span data-stu-id="1c127-104">This change corrects that error so that the method now throws the right exception.</span></span> <p/><span data-ttu-id="1c127-105">De forma predeterminada, todas las aplicaciones destinadas a .NET Framework 4.6.2 y versiones anteriores continuarán iniciando la excepción <xref:System.NullReferenceException?displayProperty=fullName> por motivos de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="1c127-105">By default all applications targeting .NET Framework 4.6.2 and earlier continue to throw <xref:System.NullReferenceException?displayProperty=fullName> for compatibility.</span></span> <span data-ttu-id="1c127-106">Los desarrolladores que seleccionen como destino .NET Framework 4.7 y versiones posteriores debería ver las excepciones correctas.</span><span class="sxs-lookup"><span data-stu-id="1c127-106">Developers targeting .NET Framework 4.7 and above should see the right exceptions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c127-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1c127-107">Suggestion</span></span>

<span data-ttu-id="1c127-108">Los desarrolladores que quieran seguir obteniendo una excepción <xref:System.NullReferenceException?displayProperty=fullName> cuando el destino sea .NET Framework 4.7 o versiones posteriores, pueden agregar o combinar lo siguiente en el archivo App.config de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="1c127-108">Developers who wish to revert to getting <xref:System.NullReferenceException?displayProperty=fullName> when targeting .NET Framework 4.7 or later can add/merge the following to their application's App.config file:</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1c127-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="1c127-109">Name</span></span>    | <span data-ttu-id="1c127-110">Valor</span><span class="sxs-lookup"><span data-stu-id="1c127-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c127-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1c127-111">Scope</span></span>   | <span data-ttu-id="1c127-112">Borde</span><span class="sxs-lookup"><span data-stu-id="1c127-112">Edge</span></span>        |
| <span data-ttu-id="1c127-113">Versión</span><span class="sxs-lookup"><span data-stu-id="1c127-113">Version</span></span> | <span data-ttu-id="1c127-114">4.7</span><span class="sxs-lookup"><span data-stu-id="1c127-114">4.7</span></span>         |
| <span data-ttu-id="1c127-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c127-115">Type</span></span>    | <span data-ttu-id="1c127-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="1c127-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1c127-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1c127-117">Affected APIs</span></span>

- <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom(System.ComponentModel.ITypeDescriptorContext,System.Globalization.CultureInfo,System.Object)?displayProperty=nameWithType>
