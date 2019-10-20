---
ms.openlocfilehash: 3d0a90a57c2b1c2759b8420e74c284668d54e9cb
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526775"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="1944c-101">API duplicadas quitadas de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1944c-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="1944c-102">En .NET Core 3.0 RC1 se han quitado una serie de API que se habían duplicado accidentalmente en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> a partir de la versión preliminar 4 de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="1944c-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1944c-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="1944c-103">Change description</span></span>

<span data-ttu-id="1944c-104">La versión preliminar 4 de .NET Core 3.0 duplicó accidentalmente varios tipos en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> que ya existían en el espacio de nombres <xref:System.ComponentModel.Design?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1944c-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="1944c-105">A partir de .NET Core 3.0 RC1, estos tipos duplicados ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="1944c-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="1944c-106">En la tabla siguiente se muestran las listas del tipo original y su tipo duplicado:</span><span class="sxs-lookup"><span data-stu-id="1944c-106">The following table shows lists the original type and its duplicated type:</span></span>

|<span data-ttu-id="1944c-107">Tipo original</span><span class="sxs-lookup"><span data-stu-id="1944c-107">Original type</span></span>|<span data-ttu-id="1944c-108">Tipo duplicado</span><span class="sxs-lookup"><span data-stu-id="1944c-108">Duplicated type</span></span>|
|---|---|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
|<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
|<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="1944c-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1944c-109">Version introduced</span></span>

<span data-ttu-id="1944c-110">3.0 RC1</span><span class="sxs-lookup"><span data-stu-id="1944c-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1944c-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1944c-111">Recommended action</span></span>

<span data-ttu-id="1944c-112">Actualice el código para hacer referencia al tipo original, como se muestra en la columna **Tipo original** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1944c-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="1944c-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="1944c-113">Category</span></span>

<span data-ttu-id="1944c-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1944c-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1944c-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1944c-115">Affected APIs</span></span>

- <span data-ttu-id="1944c-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="1944c-116">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
