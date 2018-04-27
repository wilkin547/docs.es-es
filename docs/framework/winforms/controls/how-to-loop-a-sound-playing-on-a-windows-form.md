---
title: 'Cómo: Repetir la reproducción de un sonido en Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6b4e910f30a5d125fd1ec234e896828738f62c4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="4e8b0-102">Cómo: Repetir la reproducción de un sonido en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e8b0-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="4e8b0-103">En el ejemplo de código siguiente, se reproduce repetidamente un sonido.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="4e8b0-104">Cuando se ejecuta el código en el controlador de eventos `stopPlayingButton_Click`, todos los sonidos que se estén reproduciendo se detienen.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="4e8b0-105">Si no se está reproduciendo ningún sonido, no ocurre nada.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e8b0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e8b0-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e8b0-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4e8b0-107">Compiling the Code</span></span>  
 <span data-ttu-id="4e8b0-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4e8b0-108">This example requires:</span></span>  
  
-   <span data-ttu-id="4e8b0-109">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="4e8b0-110">Que reemplace el nombre de archivo `"c:\Windows\Media\chimes.wav"` por un nombre de archivo válido.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="4e8b0-111">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-111">For information about building this example from the command line for visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4e8b0-112">También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="4e8b0-113">Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e8b0-114">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4e8b0-114">Robust Programming</span></span>  
 <span data-ttu-id="4e8b0-115">Las operaciones de archivo se deberían agregar dentro de los bloques de control de excepciones adecuados.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-115">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="4e8b0-116">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="4e8b0-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4e8b0-117">El nombre de la ruta de acceso es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-117">The path name is malformed.</span></span> <span data-ttu-id="4e8b0-118">Por ejemplo, contiene caracteres que no son válidos o es solo espacios en blanco (clase <xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-118">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="4e8b0-119">La ruta de acceso es de solo lectura (clase <xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-119">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="4e8b0-120">El nombre de la ruta de acceso es `Nothing` (clase <xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-120">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="4e8b0-121">El nombre de la ruta de acceso es demasiado largo (clase <xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-121">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="4e8b0-122">La ruta de acceso no es válida (clase <xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-122">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="4e8b0-123">La ruta de acceso es solo dos puntos ":" (clase <xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-123">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4e8b0-124">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4e8b0-124">.NET Framework Security</span></span>  
 <span data-ttu-id="4e8b0-125">No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-125">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="4e8b0-126">Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-126">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="4e8b0-127">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-127">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8b0-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e8b0-128">See Also</span></span>  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>  
 [<span data-ttu-id="4e8b0-129">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e8b0-129">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="4e8b0-130">Información general sobre la clase SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="4e8b0-130">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)
