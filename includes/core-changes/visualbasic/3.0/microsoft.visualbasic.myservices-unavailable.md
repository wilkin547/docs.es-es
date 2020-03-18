---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116379"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="f82de-101">Los tipos del espacio de nombres Microsoft.VisualBasic.MyServices no están disponibles</span><span class="sxs-lookup"><span data-stu-id="f82de-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="f82de-102">Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f82de-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f82de-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f82de-103">Version introduced</span></span>

<span data-ttu-id="f82de-104">.NET Core 3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="f82de-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="f82de-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f82de-105">Change description</span></span>

<span data-ttu-id="f82de-106">Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> estaban disponibles en algunas versiones preliminares de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="f82de-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="f82de-107">A partir del SDK de .NET Core 3.0 (versión preliminar 9), ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f82de-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="f82de-108">Los tipos se han quitado para evitar dependencias de ensamblado innecesarias o cambios importantes en las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f82de-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f82de-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f82de-109">Recommended action</span></span>

<span data-ttu-id="f82de-110">Si su código depende del uso de los tipos **Microsoft.VisualBasic.MyServices** de y sus miembros, hay tipos y miembros correspondientes en la biblioteca de clases .NET.</span><span class="sxs-lookup"><span data-stu-id="f82de-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="f82de-111">Lo siguiente es una relación de tipos **Microsoft.VisualBasic.MyServices** y de sus tipos equivalentes en la biblioteca de clases .NET:</span><span class="sxs-lookup"><span data-stu-id="f82de-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="f82de-112">Tipo Microsoft.VisualBasic.MyServices</span><span class="sxs-lookup"><span data-stu-id="f82de-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="f82de-113">Tipo de la biblioteca de clases .NET</span><span class="sxs-lookup"><span data-stu-id="f82de-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="f82de-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> para las aplicaciones de WPF y <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> para aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f82de-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="f82de-115">Tipos del espacio de nombres <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="f82de-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="f82de-116">Tipos relacionados con el registro en el espacio de nombres <xref:Microsoft.Win32></span><span class="sxs-lookup"><span data-stu-id="f82de-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="f82de-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="f82de-117">Category</span></span>

<span data-ttu-id="f82de-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f82de-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f82de-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f82de-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
