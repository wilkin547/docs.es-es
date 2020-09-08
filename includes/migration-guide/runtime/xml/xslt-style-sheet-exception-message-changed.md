---
ms.openlocfilehash: d33d75b4c2d9bc18844f66f1fcca1e2efc6f1eee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496512"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="8b018-101">Cambio del mensaje de excepción de la hoja de estilos XSLT</span><span class="sxs-lookup"><span data-stu-id="8b018-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="8b018-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8b018-102">Details</span></span>

<span data-ttu-id="8b018-103">En .NET Framework 4.5, el texto del mensaje de error cuando un archivo XSLT es demasiado complejo es &quot;The style sheet is too complex&quot; (La hoja de estilos es demasiado compleja). En versiones anteriores, el mensaje de error era &quot;Error de compilación de XSLT&quot;. El código de aplicación que se base en el texto del mensaje de error ya no funcionará.</span><span class="sxs-lookup"><span data-stu-id="8b018-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="8b018-104">Sin embargo, los tipos de excepción siguen siendo iguales, por lo que este cambio no debería tener ningún impacto real.</span><span class="sxs-lookup"><span data-stu-id="8b018-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8b018-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8b018-105">Suggestion</span></span>

<span data-ttu-id="8b018-106">Actualice cualquier código de aplicación en función del mensaje de la excepción de esta condición de error para que espere el mensaje nuevo, o bien (e incluso mejor), actualice el código para que solo dependa del tipo de excepción (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), que no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="8b018-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="8b018-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8b018-107">Name</span></span>    | <span data-ttu-id="8b018-108">Valor</span><span class="sxs-lookup"><span data-stu-id="8b018-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8b018-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8b018-109">Scope</span></span>   |<span data-ttu-id="8b018-110">Borde</span><span class="sxs-lookup"><span data-stu-id="8b018-110">Edge</span></span>|
|<span data-ttu-id="8b018-111">Versión</span><span class="sxs-lookup"><span data-stu-id="8b018-111">Version</span></span>|<span data-ttu-id="8b018-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8b018-112">4.5</span></span>|
|<span data-ttu-id="8b018-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="8b018-113">Type</span></span>|<span data-ttu-id="8b018-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8b018-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8b018-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8b018-115">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`

-->
