---
title: Procedimiento para cargar un sonido de forma asincrónica en un formulario Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 1d710f1e6d3b208365d5b1eb2524fbeeaa673c2d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185762"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="bf0e5-102">Procedimiento para cargar un sonido de forma asincrónica en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bf0e5-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="bf0e5-103">En el ejemplo de código siguiente, se carga un sonido de forma asincrónica desde una dirección URL y, a continuación, se reproduce en un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf0e5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf0e5-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf0e5-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="bf0e5-105">Compiling the Code</span></span>  
 <span data-ttu-id="bf0e5-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="bf0e5-106">This example requires:</span></span>  
  
-   <span data-ttu-id="bf0e5-107">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="bf0e5-108">Que reemplace el nombre de archivo `"http://www.tailspintoys.com/sounds/stop.wav"` por un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="bf0e5-109">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bf0e5-110">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bf0e5-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="bf0e5-111">Robust Programming</span></span>  
 <span data-ttu-id="bf0e5-112">Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-112">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="bf0e5-113">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="bf0e5-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="bf0e5-114">El nombre de la ruta de acceso es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-114">The path name is malformed.</span></span> <span data-ttu-id="bf0e5-115">Por ejemplo, contiene caracteres que no son válidos o es solo espacios en blanco (clase <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-115">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="bf0e5-116">La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-116">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="bf0e5-117">El nombre de la ruta de acceso es `Nothing` (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-117">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="bf0e5-118">El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-118">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="bf0e5-119">La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-119">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="bf0e5-120">La ruta de acceso es solo dos puntos ":" (clase <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="bf0e5-120">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bf0e5-121">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bf0e5-121">.NET Framework Security</span></span>  
 <span data-ttu-id="bf0e5-122">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-122">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="bf0e5-123">Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-123">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="bf0e5-124">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf0e5-124">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0e5-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf0e5-125">See also</span></span>

- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [<span data-ttu-id="bf0e5-126">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bf0e5-126">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
