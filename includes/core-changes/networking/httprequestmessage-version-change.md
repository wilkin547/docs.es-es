---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198560"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="2b034-101">El valor predeterminado de HttpRequestMessage.Version ha cambiado a 1.1</span><span class="sxs-lookup"><span data-stu-id="2b034-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="2b034-102">El valor predeterminado de la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> ha cambiado de 2.0 a 1.1.</span><span class="sxs-lookup"><span data-stu-id="2b034-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2b034-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2b034-103">Version introduced</span></span>

<span data-ttu-id="2b034-104">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2b034-104">.NET Core 3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="2b034-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="2b034-105">Change description</span></span>

<span data-ttu-id="2b034-106">En las versiones 1.0 a 2.0 de .NET Core, el valor predeterminado de la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> es 1.1.</span><span class="sxs-lookup"><span data-stu-id="2b034-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="2b034-107">A partir de la versión 2.1 de .NET Core, se ha cambiado a 2.1.</span><span class="sxs-lookup"><span data-stu-id="2b034-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="2b034-108">A partir de la versión 3.0 de .NET Core, el número de versión predeterminado devuelto por la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> es, una vez más, 1.1.</span><span class="sxs-lookup"><span data-stu-id="2b034-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2b034-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2b034-109">Recommended action</span></span>

<span data-ttu-id="2b034-110">Actualice el código si depende de que la propiedad <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> devuelva un valor predeterminado de 2.0.</span><span class="sxs-lookup"><span data-stu-id="2b034-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="2b034-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="2b034-111">Category</span></span>

<span data-ttu-id="2b034-112">Redes</span><span class="sxs-lookup"><span data-stu-id="2b034-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2b034-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2b034-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

