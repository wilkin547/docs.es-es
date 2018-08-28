---
title: Acceso a los recursos del equipo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
ms.openlocfilehash: 7128a71f28d1755a14fcda5f09bee11202ab4154
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001906"
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="a33e0-102">Acceso a los recursos del equipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a33e0-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="a33e0-103">El objeto `My.Computer` es uno de los tres objetos centrales de `My` que proporcionan acceso a información y funciones de uso frecuente.</span><span class="sxs-lookup"><span data-stu-id="a33e0-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="a33e0-104">`My.Computer` proporciona los métodos, propiedades y eventos para obtener acceso al equipo donde se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a33e0-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="a33e0-105">Entre sus objetos se incluyen:</span><span class="sxs-lookup"><span data-stu-id="a33e0-105">Its objects include:</span></span>  
  
-   <xref:Microsoft.VisualBasic.Devices.Audio>
-   <span data-ttu-id="a33e0-106">Portapapeles (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span><span class="sxs-lookup"><span data-stu-id="a33e0-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
-   <xref:Microsoft.VisualBasic.Devices.Clock>
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem>
-   <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
-   <xref:Microsoft.VisualBasic.Devices.Keyboard>
-   <xref:Microsoft.VisualBasic.Devices.Mouse>
-   <xref:Microsoft.VisualBasic.Devices.Network>
-   <xref:Microsoft.VisualBasic.Devices.Ports>
-   <span data-ttu-id="a33e0-107">Registro (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span><span class="sxs-lookup"><span data-stu-id="a33e0-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a33e0-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a33e0-108">In this section</span></span>

<span data-ttu-id="a33e0-109">[Reproducir sonidos](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-109">[Playing Sounds](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span></span>  
<span data-ttu-id="a33e0-110">Muestra las tareas asociadas a `My.Computer.Audio`, como reproducir un sonido en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a33e0-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

<span data-ttu-id="a33e0-111">[Almacenar y leer datos en el Portapapeles](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-111">[Storing Data to and Reading from the Clipboard](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span></span>  
<span data-ttu-id="a33e0-112">Muestra las tareas asociadas a `My.Computer.Clipboard`, como leer datos del Portapapeles o escribir datos en él.</span><span class="sxs-lookup"><span data-stu-id="a33e0-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

<span data-ttu-id="a33e0-113">[Obtener información acerca del equipo](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-113">[Getting Information about the Computer](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span></span>  
<span data-ttu-id="a33e0-114">Muestra las tareas asociadas a `My.Computer.Info`, como determinar el nombre completo o las direcciones IP de un equipo.</span><span class="sxs-lookup"><span data-stu-id="a33e0-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

<span data-ttu-id="a33e0-115">[Acceso al teclado](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-115">[Accessing the Keyboard](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span></span>  
<span data-ttu-id="a33e0-116">Muestra las tareas asociadas a `My.Computer.Keyboard`, como determinar si BLOQ MAYÚS está activado.</span><span class="sxs-lookup"><span data-stu-id="a33e0-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

<span data-ttu-id="a33e0-117">[Acceso al mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-117">[Accessing the Mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span></span>  
<span data-ttu-id="a33e0-118">Muestra las tareas asociadas a `My.Computer.Mouse`, como determinar si un mouse está presente.</span><span class="sxs-lookup"><span data-stu-id="a33e0-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

<span data-ttu-id="a33e0-119">[Realizar operaciones de red](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-119">[Performing Network Operations](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span></span>  
<span data-ttu-id="a33e0-120">Muestra las tareas asociadas a `My.Computer.Network`, como cargar o descargar archivos.</span><span class="sxs-lookup"><span data-stu-id="a33e0-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

<span data-ttu-id="a33e0-121">[Acceso a los puertos del equipo](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-121">[Accessing the Computer's Ports](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span></span>  
<span data-ttu-id="a33e0-122">Muestra las tareas asociadas a `My.Computer.Ports`, como mostrar los puertos serie disponibles o enviar cadenas a los puertos serie.</span><span class="sxs-lookup"><span data-stu-id="a33e0-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

<span data-ttu-id="a33e0-123">[Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="a33e0-123">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
<span data-ttu-id="a33e0-124">Muestra las tareas asociadas a `My.Computer.Registry`, como leer datos de las claves del Registro o escribir datos en ellas.</span><span class="sxs-lookup"><span data-stu-id="a33e0-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
