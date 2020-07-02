---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621834"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="e4686-101">El corrector ortográfico de WPF inicia la excepción ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="e4686-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="e4686-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e4686-102">Details</span></span>

<span data-ttu-id="e4686-103">En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e4686-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="e4686-104">Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa.</span><span class="sxs-lookup"><span data-stu-id="e4686-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="e4686-105">Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.</span><span class="sxs-lookup"><span data-stu-id="e4686-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e4686-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e4686-106">Suggestion</span></span>

<span data-ttu-id="e4686-107">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e4686-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="e4686-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e4686-108">Name</span></span>    | <span data-ttu-id="e4686-109">Valor</span><span class="sxs-lookup"><span data-stu-id="e4686-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e4686-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e4686-110">Scope</span></span>   |<span data-ttu-id="e4686-111">Borde</span><span class="sxs-lookup"><span data-stu-id="e4686-111">Edge</span></span>|
|<span data-ttu-id="e4686-112">Versión</span><span class="sxs-lookup"><span data-stu-id="e4686-112">Version</span></span>|<span data-ttu-id="e4686-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e4686-113">4.6.1</span></span>|
|<span data-ttu-id="e4686-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="e4686-114">Type</span></span>|<span data-ttu-id="e4686-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e4686-115">Runtime</span></span>|
