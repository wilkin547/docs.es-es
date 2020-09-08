---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497303"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="510c0-101">Actualización de la pila de impresión de WPF</span><span class="sxs-lookup"><span data-stu-id="510c0-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="510c0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="510c0-102">Details</span></span>

<span data-ttu-id="510c0-103">Las API de impresión de WPF en las que se usa <xref:System.Printing.PrintQueue?displayProperty=fullName> ahora llaman a la API Print Document Package de Windows en lugar de la API XPS Print, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="510c0-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="510c0-104">El cambio se realizó con la facilidad en mente; ni los usuarios ni los desarrolladores deberían percibir cambios en el comportamiento o el uso de la API.</span><span class="sxs-lookup"><span data-stu-id="510c0-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="510c0-105">La nueva pila de impresión está habilitada de forma predeterminada cuando se ejecuta en Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="510c0-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="510c0-106">La pila de impresión antigua seguirá funcionando como antes en las versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="510c0-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="510c0-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="510c0-107">Suggestion</span></span>

<span data-ttu-id="510c0-108">Para usar la pila antigua en Windows 10 Creators Update, establezca el valor <code>UseXpsOMPrinting</code> REG_DWORD de la clave del Registro <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> en <code>1</code>.</span><span class="sxs-lookup"><span data-stu-id="510c0-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="510c0-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="510c0-109">Name</span></span>    | <span data-ttu-id="510c0-110">Valor</span><span class="sxs-lookup"><span data-stu-id="510c0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="510c0-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="510c0-111">Scope</span></span>   |<span data-ttu-id="510c0-112">Borde</span><span class="sxs-lookup"><span data-stu-id="510c0-112">Edge</span></span>|
|<span data-ttu-id="510c0-113">Versión</span><span class="sxs-lookup"><span data-stu-id="510c0-113">Version</span></span>|<span data-ttu-id="510c0-114">4.7</span><span class="sxs-lookup"><span data-stu-id="510c0-114">4.7</span></span>|
|<span data-ttu-id="510c0-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="510c0-115">Type</span></span>|<span data-ttu-id="510c0-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="510c0-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="510c0-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="510c0-117">Affected APIs</span></span>

<span data-ttu-id="510c0-118">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="510c0-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
