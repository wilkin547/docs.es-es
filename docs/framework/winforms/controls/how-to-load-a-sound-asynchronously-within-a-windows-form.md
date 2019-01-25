---
title: Procedimiento Cargar un sonido de forma asincrónica en un formulario de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: ed1257a942eb990c9b0c6427d264013e3324326b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523680"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="b86ae-102">Procedimiento Cargar un sonido de forma asincrónica en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="b86ae-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="b86ae-103">En el ejemplo de código siguiente, se carga un sonido de forma asincrónica desde una dirección URL y, a continuación, se reproduce en un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="b86ae-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b86ae-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b86ae-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b86ae-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b86ae-105">Compiling the Code</span></span>  
 <span data-ttu-id="b86ae-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b86ae-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b86ae-107">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b86ae-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="b86ae-108">Que reemplace el nombre de archivo `"http://www.tailspintoys.com/sounds/stop.wav"` por un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="b86ae-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="b86ae-109">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b86ae-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b86ae-110">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="b86ae-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="b86ae-111">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b86ae-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b86ae-112">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b86ae-112">Robust Programming</span></span>  
 <span data-ttu-id="b86ae-113">Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.</span><span class="sxs-lookup"><span data-stu-id="b86ae-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="b86ae-114">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="b86ae-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b86ae-115">El nombre de la ruta de acceso es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="b86ae-115">The path name is malformed.</span></span> <span data-ttu-id="b86ae-116">Por ejemplo, contiene caracteres que no son válidos o es solo espacios en blanco (clase <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="b86ae-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="b86ae-117">La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b86ae-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="b86ae-118">El nombre de la ruta de acceso es `Nothing` (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="b86ae-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="b86ae-119">El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="b86ae-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="b86ae-120">La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="b86ae-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="b86ae-121">La ruta de acceso es solo dos puntos ":" (clase <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="b86ae-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b86ae-122">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b86ae-122">.NET Framework Security</span></span>  
 <span data-ttu-id="b86ae-123">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="b86ae-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="b86ae-124">Por ejemplo, es posible que el archivo `Form1.vb` no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b86ae-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="b86ae-125">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b86ae-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b86ae-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b86ae-126">See also</span></span>
- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [<span data-ttu-id="b86ae-127">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b86ae-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
