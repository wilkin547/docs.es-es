---
ms.openlocfilehash: 58e65bae1593f23945a971b896a1db4a929b4587
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198561"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="9aede-101">Los tipos del espacio de nombres Microsoft.VisualBasic.MyServices no están disponibles</span><span class="sxs-lookup"><span data-stu-id="9aede-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="9aede-102">Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9aede-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9aede-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="9aede-103">Version introduced</span></span>

<span data-ttu-id="9aede-104">.NET Core 3.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="9aede-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="9aede-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="9aede-105">Change description</span></span>

<span data-ttu-id="9aede-106">Los tipos del espacio de nombres <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> estaban disponibles en algunas versiones preliminares de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9aede-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="9aede-107">A partir del SDK de .NET Core 3.0 (versión preliminar 9), ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9aede-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="9aede-108">Los tipos se han quitado para evitar dependencias de ensamblado innecesarias o cambios importantes en las versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="9aede-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9aede-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="9aede-109">Recommended action</span></span>

<span data-ttu-id="9aede-110">Si su código depende del uso de los tipos **Microsoft.VisualBasic.MyServices** de y sus miembros, hay tipos y miembros correspondientes en la biblioteca de clases .NET.</span><span class="sxs-lookup"><span data-stu-id="9aede-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="9aede-111">Lo siguiente es una relación de tipos **Microsoft.VisualBasic.MyServices** y de sus tipos equivalentes en la biblioteca de clases .NET:</span><span class="sxs-lookup"><span data-stu-id="9aede-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="9aede-112">Tipo Microsoft.VisualBasic.MyServices</span><span class="sxs-lookup"><span data-stu-id="9aede-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="9aede-113">Tipo de la biblioteca de clases .NET</span><span class="sxs-lookup"><span data-stu-id="9aede-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="9aede-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> para las aplicaciones de WPF y <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> para aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9aede-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="9aede-115">Tipos del espacio de nombres <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="9aede-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="9aede-116">Tipos relacionados con el registro en el espacio de nombres <xref:Microsoft.Win32></span><span class="sxs-lookup"><span data-stu-id="9aede-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="9aede-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="9aede-117">Category</span></span>

<span data-ttu-id="9aede-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9aede-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9aede-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9aede-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

