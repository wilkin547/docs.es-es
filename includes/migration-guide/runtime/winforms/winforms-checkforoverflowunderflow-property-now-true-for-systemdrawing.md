---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379667"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="11ed5-101">La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing</span><span class="sxs-lookup"><span data-stu-id="11ed5-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="11ed5-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="11ed5-102">Details</span></span>|<span data-ttu-id="11ed5-103">La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.</span><span class="sxs-lookup"><span data-stu-id="11ed5-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="11ed5-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="11ed5-104">Suggestion</span></span>|<span data-ttu-id="11ed5-105">Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa.</span><span class="sxs-lookup"><span data-stu-id="11ed5-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="11ed5-106">Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="11ed5-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="11ed5-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="11ed5-107">Scope</span></span>|<span data-ttu-id="11ed5-108">Borde</span><span class="sxs-lookup"><span data-stu-id="11ed5-108">Edge</span></span>|
|<span data-ttu-id="11ed5-109">Versión</span><span class="sxs-lookup"><span data-stu-id="11ed5-109">Version</span></span>|<span data-ttu-id="11ed5-110">4.5</span><span class="sxs-lookup"><span data-stu-id="11ed5-110">4.5</span></span>|
|<span data-ttu-id="11ed5-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="11ed5-111">Type</span></span>|<span data-ttu-id="11ed5-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="11ed5-112">Runtime</span></span>|
