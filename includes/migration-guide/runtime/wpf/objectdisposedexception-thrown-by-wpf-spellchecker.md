---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774226"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="ebf25-101">El corrector ortográfico de WPF inicia la excepción ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="ebf25-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ebf25-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ebf25-102">Details</span></span>|<span data-ttu-id="ebf25-103">En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="ebf25-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="ebf25-104">Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa.</span><span class="sxs-lookup"><span data-stu-id="ebf25-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="ebf25-105">Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.</span><span class="sxs-lookup"><span data-stu-id="ebf25-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="ebf25-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ebf25-106">Suggestion</span></span>|<span data-ttu-id="ebf25-107">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="ebf25-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="ebf25-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ebf25-108">Scope</span></span>|<span data-ttu-id="ebf25-109">Borde</span><span class="sxs-lookup"><span data-stu-id="ebf25-109">Edge</span></span>|
|<span data-ttu-id="ebf25-110">Versión</span><span class="sxs-lookup"><span data-stu-id="ebf25-110">Version</span></span>|<span data-ttu-id="ebf25-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="ebf25-111">4.6.1</span></span>|
|<span data-ttu-id="ebf25-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ebf25-112">Type</span></span>|<span data-ttu-id="ebf25-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ebf25-113">Runtime</span></span>|
