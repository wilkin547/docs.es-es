---
ms.openlocfilehash: 9e9e443be9ea51d214e95c676fc28f0d8790af8b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117174"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="15342-101">La configuración regional de “C” se asigna a la configuración regional invariable</span><span class="sxs-lookup"><span data-stu-id="15342-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="15342-102">.NET Core 2.2 y las versiones anteriores dependen del comportamiento predeterminado de ICU, el cual asigna la configuración regional de “C” a la configuración regional en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="15342-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="15342-103">La configuración regional en_US_POSIX tiene un comportamiento de intercalación no deseado, porque no admite comparaciones de cadenas que no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="15342-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="15342-104">Algunas distribuciones de Linux establecían la configuración regional de “C” como la configuración regional predeterminada, por lo que los usuarios experimentaban un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="15342-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span> 

#### <a name="details"></a><span data-ttu-id="15342-105">Detalles</span><span class="sxs-lookup"><span data-stu-id="15342-105">Details</span></span>

<span data-ttu-id="15342-106">A partir de .NET Core 3.0, la asignación de la configuración regional de “C” ha cambiado para usar la configuración regional invariable en lugar de en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="15342-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="15342-107">La configuración regional de “C” con la asignación invariable también se aplica a Windows para mantener la coherencia.</span><span class="sxs-lookup"><span data-stu-id="15342-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="15342-108">La asignación de “C” a la referencia cultural en_US_POSIX causaba confusión entre los clientes porque en_US_POSIX no admite operaciones de ordenación y búsqueda de cadenas que no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="15342-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="15342-109">Dado que la configuración regional de “C” se usa como configuración regional predeterminada en algunas de las distribuciones de Linux, los clientes experimentaron este comportamiento no deseado en estos sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="15342-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="15342-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="15342-110">Version introduced</span></span>

<span data-ttu-id="15342-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="15342-111">.NET Core 3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="15342-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="15342-112">Recommended action</span></span>

<span data-ttu-id="15342-113">Nada más aparte de conocer este cambio.</span><span class="sxs-lookup"><span data-stu-id="15342-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="15342-114">Este cambio solo afecta a las aplicaciones que usan la asignación de configuración regional de “C”.</span><span class="sxs-lookup"><span data-stu-id="15342-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="15342-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="15342-115">Category</span></span>

<span data-ttu-id="15342-116">Globalización</span><span class="sxs-lookup"><span data-stu-id="15342-116">Globalization</span></span> 

### <a name="affected-apis"></a><span data-ttu-id="15342-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="15342-117">Affected APIs</span></span>

<span data-ttu-id="15342-118">Este cambio afecta a todas las API de intercalación y de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="15342-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
