---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496256"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="28985-101">Los datos escritos en PrintSystemJobInfo.JobStream deben estar en formato XPS</span><span class="sxs-lookup"><span data-stu-id="28985-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="28985-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="28985-102">Details</span></span>

<span data-ttu-id="28985-103">La propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> expone la secuencia de un trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="28985-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="28985-104">El usuario puede enviar datos sin formato a los componentes de impresión del sistema operativo subyacente si escribe en esta secuencia. A partir de .NET Framework 4.5 en Windows 8 y versiones posteriores del sistema operativo Windows, los datos que se escriben en esta secuencia deben estar en formato XPS como una secuencia de paquete.</span><span class="sxs-lookup"><span data-stu-id="28985-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="28985-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="28985-105">Suggestion</span></span>

<span data-ttu-id="28985-106">Para mostrar contenido de impresión, puede realizar una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="28985-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="28985-107">Utilice la clase <xref:System.Windows.Xps.XpsDocumentWriter> para mostrar contenido de impresión.</span><span class="sxs-lookup"><span data-stu-id="28985-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="28985-108">Esta es la alternativa recomendada.</span><span class="sxs-lookup"><span data-stu-id="28985-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="28985-109">Asegúrese de que los datos enviados a la secuencia que devuelve la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> están en formato XPS como una secuencia de paquete.</span><span class="sxs-lookup"><span data-stu-id="28985-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="28985-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="28985-110">Name</span></span>    | <span data-ttu-id="28985-111">Valor</span><span class="sxs-lookup"><span data-stu-id="28985-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="28985-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="28985-112">Scope</span></span>   |<span data-ttu-id="28985-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="28985-113">Minor</span></span>|
|<span data-ttu-id="28985-114">Versión</span><span class="sxs-lookup"><span data-stu-id="28985-114">Version</span></span>|<span data-ttu-id="28985-115">4.5</span><span class="sxs-lookup"><span data-stu-id="28985-115">4.5</span></span>|
|<span data-ttu-id="28985-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="28985-116">Type</span></span>|<span data-ttu-id="28985-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="28985-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="28985-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="28985-118">Affected APIs</span></span>

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->
