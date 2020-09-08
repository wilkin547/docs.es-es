---
ms.openlocfilehash: f61e5670334f4d3674fd0b008d1a476b14c7ba4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497547"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="a72c8-101">Las llamadas a Attribute.GetCustomAttributes en una propiedad de indizador ya no inician excepciones AmbiguousMatchException si es posible resolver la ambigüedad por el tipo de índice</span><span class="sxs-lookup"><span data-stu-id="a72c8-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

#### <a name="details"></a><span data-ttu-id="a72c8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a72c8-102">Details</span></span>

<span data-ttu-id="a72c8-103">Antes de .NET Framework 4.6, llamar a <code>GetCustomAttribute(s)</code> en una propiedad de indizador que difiriera de otra propiedad solo en el tipo de índice daba lugar a una instancia de <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="a72c8-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span></span> <span data-ttu-id="a72c8-104">A partir de .NET Framework 4.6, los atributos de la propiedad se devolverán correctamente.</span><span class="sxs-lookup"><span data-stu-id="a72c8-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a72c8-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a72c8-105">Suggestion</span></span>

<span data-ttu-id="a72c8-106">Tenga en cuenta que GetCustomAttribute(s) ahora funcionará con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="a72c8-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="a72c8-107">Si anteriormente alguna aplicación se basaba en el elemento <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, ahora se debería usar una reflexión para buscar varios indizadores de forma explícita en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a72c8-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>

| <span data-ttu-id="a72c8-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a72c8-108">Name</span></span>    | <span data-ttu-id="a72c8-109">Valor</span><span class="sxs-lookup"><span data-stu-id="a72c8-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a72c8-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a72c8-110">Scope</span></span>   |<span data-ttu-id="a72c8-111">Borde</span><span class="sxs-lookup"><span data-stu-id="a72c8-111">Edge</span></span>|
|<span data-ttu-id="a72c8-112">Versión</span><span class="sxs-lookup"><span data-stu-id="a72c8-112">Version</span></span>|<span data-ttu-id="a72c8-113">4.6</span><span class="sxs-lookup"><span data-stu-id="a72c8-113">4.6</span></span>|
|<span data-ttu-id="a72c8-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="a72c8-114">Type</span></span>|<span data-ttu-id="a72c8-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a72c8-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a72c8-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a72c8-116">Affected APIs</span></span>

- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo,System.Boolean)``
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo,System.Boolean)``

-->
