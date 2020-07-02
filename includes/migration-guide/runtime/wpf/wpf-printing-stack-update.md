---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621407"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="4fd9c-101">Actualización de la pila de impresión de WPF</span><span class="sxs-lookup"><span data-stu-id="4fd9c-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="4fd9c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4fd9c-102">Details</span></span>

<span data-ttu-id="4fd9c-103">Las API de impresión de WPF en las que se usa <xref:System.Printing.PrintQueue?displayProperty=fullName> ahora llaman a la API Print Document Package de Windows en lugar de la API XPS Print, que está en desuso.</span><span class="sxs-lookup"><span data-stu-id="4fd9c-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="4fd9c-104">El cambio se realizó con la facilidad en mente; ni los usuarios ni los desarrolladores deberían percibir cambios en el comportamiento o el uso de la API.</span><span class="sxs-lookup"><span data-stu-id="4fd9c-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="4fd9c-105">La nueva pila de impresión está habilitada de forma predeterminada cuando se ejecuta en Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="4fd9c-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="4fd9c-106">La pila de impresión antigua seguirá funcionando como antes en las versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="4fd9c-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4fd9c-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4fd9c-107">Suggestion</span></span>

<span data-ttu-id="4fd9c-108">Para usar la pila antigua en Windows 10 Creators Update, establezca el valor <code>UseXpsOMPrinting</code> REG_DWORD de la clave del Registro <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> en <code>1</code>.</span><span class="sxs-lookup"><span data-stu-id="4fd9c-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="4fd9c-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="4fd9c-109">Name</span></span>    | <span data-ttu-id="4fd9c-110">Valor</span><span class="sxs-lookup"><span data-stu-id="4fd9c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4fd9c-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4fd9c-111">Scope</span></span>   |<span data-ttu-id="4fd9c-112">Borde</span><span class="sxs-lookup"><span data-stu-id="4fd9c-112">Edge</span></span>|
|<span data-ttu-id="4fd9c-113">Versión</span><span class="sxs-lookup"><span data-stu-id="4fd9c-113">Version</span></span>|<span data-ttu-id="4fd9c-114">4.7</span><span class="sxs-lookup"><span data-stu-id="4fd9c-114">4.7</span></span>|
|<span data-ttu-id="4fd9c-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="4fd9c-115">Type</span></span>|<span data-ttu-id="4fd9c-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4fd9c-116">Runtime</span></span>|
