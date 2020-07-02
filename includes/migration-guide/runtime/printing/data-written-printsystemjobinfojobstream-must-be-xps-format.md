---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620644"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a><span data-ttu-id="71098-101">Los datos escritos en PrintSystemJobInfo.JobStream deben estar en formato XPS</span><span class="sxs-lookup"><span data-stu-id="71098-101">Data written to PrintSystemJobInfo.JobStream must be in XPS format</span></span>

#### <a name="details"></a><span data-ttu-id="71098-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="71098-102">Details</span></span>

<span data-ttu-id="71098-103">La propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> expone la secuencia de un trabajo de impresión.</span><span class="sxs-lookup"><span data-stu-id="71098-103">The <xref:System.Printing.PrintSystemJobInfo.JobStream> property exposes the stream of a print job.</span></span> <span data-ttu-id="71098-104">El usuario puede enviar datos sin formato a los componentes de impresión del sistema operativo subyacente si escribe en esta secuencia. A partir de .NET Framework 4.5 en Windows 8 y versiones posteriores del sistema operativo Windows, los datos que se escriben en esta secuencia deben estar en formato XPS como una secuencia de paquete.</span><span class="sxs-lookup"><span data-stu-id="71098-104">The user can send raw data to the underlying operating system printing components by writing to this stream.Starting with the .NET Framework 4.5 on Windows 8 and later versions of the Windows operating system, data written to this stream must be in XPS format as a package stream.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="71098-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="71098-105">Suggestion</span></span>

<span data-ttu-id="71098-106">Para mostrar contenido de impresión, puede realizar una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="71098-106">To output print content, you can do either of the following:</span></span><ul><li><span data-ttu-id="71098-107">Utilice la clase <xref:System.Windows.Xps.XpsDocumentWriter> para mostrar contenido de impresión.</span><span class="sxs-lookup"><span data-stu-id="71098-107">Use the <xref:System.Windows.Xps.XpsDocumentWriter> class to output print content.</span></span> <span data-ttu-id="71098-108">Esta es la alternativa recomendada.</span><span class="sxs-lookup"><span data-stu-id="71098-108">This is the recommended alternative.</span></span></li><li><span data-ttu-id="71098-109">Asegúrese de que los datos enviados a la secuencia que devuelve la propiedad <xref:System.Printing.PrintSystemJobInfo.JobStream> están en formato XPS como una secuencia de paquete.</span><span class="sxs-lookup"><span data-stu-id="71098-109">Ensure that the data sent to the stream returned by the <xref:System.Printing.PrintSystemJobInfo.JobStream> property is in XPS format as a package stream.</span></span></li></ul>

| <span data-ttu-id="71098-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="71098-110">Name</span></span>    | <span data-ttu-id="71098-111">Valor</span><span class="sxs-lookup"><span data-stu-id="71098-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="71098-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="71098-112">Scope</span></span>   |<span data-ttu-id="71098-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="71098-113">Minor</span></span>|
|<span data-ttu-id="71098-114">Versión</span><span class="sxs-lookup"><span data-stu-id="71098-114">Version</span></span>|<span data-ttu-id="71098-115">4.5</span><span class="sxs-lookup"><span data-stu-id="71098-115">4.5</span></span>|
|<span data-ttu-id="71098-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="71098-116">Type</span></span>|<span data-ttu-id="71098-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="71098-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="71098-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="71098-118">Affected APIs</span></span>

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
