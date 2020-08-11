---
ms.openlocfilehash: 4fb1ffed97a5b7f906bed13a69f1e71563d11dae
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556218"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="b9295-101">Se ha quitado el atributo SerializableAttribute de algunos tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9295-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="b9295-102">El atributo <xref:System.SerializableAttribute> se ha quitado de algunas clases de Windows Forms que no tienen ningún escenario de serialización binaria conocido.</span><span class="sxs-lookup"><span data-stu-id="b9295-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b9295-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b9295-103">Change description</span></span>

<span data-ttu-id="b9295-104">Los tipos siguientes se representan con el atributo <xref:System.SerializableAttribute> en .NET Framework, pero este atributo se ha quitado en .NET Core:</span><span class="sxs-lookup"><span data-stu-id="b9295-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="b9295-105">Históricamente, este mecanismo de serialización ha presentado problemas graves de mantenimiento y de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b9295-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="b9295-106">Mantener el atributo `SerializableAttribute` en tipos significa que se deben comprobar esos tipos por si hay cambios de serialización de una versión a otra y, posiblemente, también de un marco a otro.</span><span class="sxs-lookup"><span data-stu-id="b9295-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="b9295-107">Esto dificulta el desarrollo de esos tipos y puede requerir un mantenimiento costoso.</span><span class="sxs-lookup"><span data-stu-id="b9295-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="b9295-108">Estos tipos no tienen ningún escenario conocido de serialización binaria, lo cual reduce el impacto de la eliminación del atributo.</span><span class="sxs-lookup"><span data-stu-id="b9295-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="b9295-109">Para obtener más información, vea [Serialización binaria](~/docs/standard/serialization/binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b9295-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b9295-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b9295-110">Version introduced</span></span>

<span data-ttu-id="b9295-111">3.0</span><span class="sxs-lookup"><span data-stu-id="b9295-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b9295-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b9295-112">Recommended action</span></span>

<span data-ttu-id="b9295-113">Actualice cualquier código que pueda depender de estos tipos que están marcados como serializables.</span><span class="sxs-lookup"><span data-stu-id="b9295-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="b9295-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="b9295-114">Category</span></span>

<span data-ttu-id="b9295-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9295-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b9295-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b9295-116">Affected APIs</span></span>

- <span data-ttu-id="b9295-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b9295-117">None</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
