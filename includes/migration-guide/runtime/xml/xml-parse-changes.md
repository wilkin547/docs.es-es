---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009075"
---
### <a name="xml-parsing-changes"></a><span data-ttu-id="85c53-101">Cambios de análisis en XML</span><span class="sxs-lookup"><span data-stu-id="85c53-101">XML parsing changes</span></span>

| <span data-ttu-id="85c53-102">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="85c53-102">Name</span></span>    | <span data-ttu-id="85c53-103">Valor</span><span class="sxs-lookup"><span data-stu-id="85c53-103">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="85c53-104">Ámbito</span><span class="sxs-lookup"><span data-stu-id="85c53-104">Scope</span></span>   | <span data-ttu-id="85c53-105">Secundaria</span><span class="sxs-lookup"><span data-stu-id="85c53-105">Minor</span></span>   |
| <span data-ttu-id="85c53-106">Versión</span><span class="sxs-lookup"><span data-stu-id="85c53-106">Version</span></span> | <span data-ttu-id="85c53-107">4.5.2</span><span class="sxs-lookup"><span data-stu-id="85c53-107">4.5.2</span></span>   |
| <span data-ttu-id="85c53-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="85c53-108">Type</span></span>    | <span data-ttu-id="85c53-109">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="85c53-109">Runtime</span></span> |

#### <a name="details"></a><span data-ttu-id="85c53-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="85c53-110">Details</span></span>

<span data-ttu-id="85c53-111">Por motivos de seguridad, se han efectuado los cambios siguientes en las API de análisis en XML:</span><span class="sxs-lookup"><span data-stu-id="85c53-111">For security reasons, the following changes were introduced into XML parsing APIS:</span></span>

- <span data-ttu-id="85c53-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> se ha establecido en 10 millones al inicializar <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="85c53-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> is set to 10 million when <xref:System.Xml.XmlReaderSettings> is initialized.</span></span>
- <span data-ttu-id="85c53-113">De forma predeterminada, la propiedad <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="85c53-113"><xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> is set to `null` by default.</span></span>

> [!NOTE]
> <span data-ttu-id="85c53-114">Todos los analizadores en XML usan <xref:System.Xml.XmlReaderSettings>, por lo que, aunque este cambio ayuda al caso <xref:System.Xml.XmlReader>, también afecta a otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="85c53-114"><xref:System.Xml.XmlReaderSettings> is used by all XML parsers, so while this change helps the <xref:System.Xml.XmlReader> case, it also affects other scenarios.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85c53-115">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="85c53-115">Suggestion</span></span>

<span data-ttu-id="85c53-116">Para revertir el comportamiento a uno anterior, puede establecer un valor en el registro.</span><span class="sxs-lookup"><span data-stu-id="85c53-116">To revert to the previous behavior, you can set a value in the registry.</span></span> <span data-ttu-id="85c53-117">Agregue un valor DWORD denominado `EnableLegacyXmlSettings` a la clave del registro `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` y establezca su valor en `1`.</span><span class="sxs-lookup"><span data-stu-id="85c53-117">Add a DWORD value named `EnableLegacyXmlSettings` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` registry key, and set its value to `1`.</span></span> <span data-ttu-id="85c53-118">También puede agregar el valor del registro en el subárbol HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="85c53-118">You can also add the registry value in the HKEY_CURRENT_USER hive instead.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="85c53-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="85c53-119">Affected APIs</span></span>

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

<span data-ttu-id="85c53-120">Además, afectará a cualquier API XML que dependa de <xref:System.Xml.XmlResolver>, ya sea directa o indirectamente.</span><span class="sxs-lookup"><span data-stu-id="85c53-120">In addition, any XML API that depends on <xref:System.Xml.XmlResolver>, either directly or indirectly, is affected.</span></span>

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
