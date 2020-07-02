---
ms.openlocfilehash: 5c27e8acdf30533036546ba4cca9e06877bde362
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620734"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="f31f3-101">Cambio del mensaje de excepción de la hoja de estilos XSLT</span><span class="sxs-lookup"><span data-stu-id="f31f3-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="f31f3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f31f3-102">Details</span></span>

<span data-ttu-id="f31f3-103">En .NET Framework 4.5, el texto del mensaje de error cuando un archivo XSLT es demasiado complejo es &quot;The style sheet is too complex&quot; (La hoja de estilos es demasiado compleja). En versiones anteriores, el mensaje de error era &quot;Error de compilación de XSLT&quot;. El código de aplicación que se base en el texto del mensaje de error ya no funcionará.</span><span class="sxs-lookup"><span data-stu-id="f31f3-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="f31f3-104">Sin embargo, los tipos de excepción siguen siendo iguales, por lo que este cambio no debería tener ningún impacto real.</span><span class="sxs-lookup"><span data-stu-id="f31f3-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f31f3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f31f3-105">Suggestion</span></span>

<span data-ttu-id="f31f3-106">Actualice cualquier código de aplicación en función del mensaje de la excepción de esta condición de error para que espere el mensaje nuevo, o bien (e incluso mejor), actualice el código para que solo dependa del tipo de excepción (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), que no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="f31f3-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="f31f3-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f31f3-107">Name</span></span>    | <span data-ttu-id="f31f3-108">Valor</span><span class="sxs-lookup"><span data-stu-id="f31f3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f31f3-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f31f3-109">Scope</span></span>   |<span data-ttu-id="f31f3-110">Borde</span><span class="sxs-lookup"><span data-stu-id="f31f3-110">Edge</span></span>|
|<span data-ttu-id="f31f3-111">Versión</span><span class="sxs-lookup"><span data-stu-id="f31f3-111">Version</span></span>|<span data-ttu-id="f31f3-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f31f3-112">4.5</span></span>|
|<span data-ttu-id="f31f3-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="f31f3-113">Type</span></span>|<span data-ttu-id="f31f3-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f31f3-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f31f3-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f31f3-115">Affected APIs</span></span>

-<xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
