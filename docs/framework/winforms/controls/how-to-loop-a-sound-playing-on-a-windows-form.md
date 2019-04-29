---
title: Procedimiento para repetir un sonido reproducido en un formulario Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
ms.openlocfilehash: a74acbbbcb5646a35de54a6000a0feae30f145a5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638917"
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="1c6cc-102">Procedimiento para repetir un sonido reproducido en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c6cc-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="1c6cc-103">En el ejemplo de código siguiente, se reproduce repetidamente un sonido.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="1c6cc-104">Cuando se ejecuta el código en el controlador de eventos `stopPlayingButton_Click`, todos los sonidos que se estén reproduciendo se detienen.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="1c6cc-105">Si no se está reproduciendo ningún sonido, no ocurre nada.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c6cc-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c6cc-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c6cc-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1c6cc-107">Compiling the Code</span></span>  
 <span data-ttu-id="1c6cc-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1c6cc-108">This example requires:</span></span>  
  
- <span data-ttu-id="1c6cc-109">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="1c6cc-110">Que reemplace el nombre de archivo `"c:\Windows\Media\chimes.wav"` por un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="1c6cc-111">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1c6cc-112">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1c6cc-113">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1c6cc-113">Robust Programming</span></span>  
 <span data-ttu-id="1c6cc-114">Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-114">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="1c6cc-115">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="1c6cc-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="1c6cc-116">El nombre de la ruta de acceso es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-116">The path name is malformed.</span></span> <span data-ttu-id="1c6cc-117">Por ejemplo, contiene caracteres que no son válidos o es solo espacios en blanco (clase <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-117">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
- <span data-ttu-id="1c6cc-118">La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-118">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
- <span data-ttu-id="1c6cc-119">El nombre de la ruta de acceso es `Nothing` (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-119">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
- <span data-ttu-id="1c6cc-120">El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-120">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
- <span data-ttu-id="1c6cc-121">La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-121">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
- <span data-ttu-id="1c6cc-122">La ruta de acceso es solo dos puntos ":" (clase <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="1c6cc-122">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1c6cc-123">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1c6cc-123">.NET Framework Security</span></span>  
 <span data-ttu-id="1c6cc-124">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-124">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="1c6cc-125">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-125">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="1c6cc-126">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1c6cc-126">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6cc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c6cc-127">See also</span></span>

- <xref:System.Media.SoundPlayer.PlayLooping%2A>
- [<span data-ttu-id="1c6cc-128">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c6cc-128">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="1c6cc-129">Información general sobre la clase SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="1c6cc-129">SoundPlayer Class Overview</span></span>](soundplayer-class-overview.md)
