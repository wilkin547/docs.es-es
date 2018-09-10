---
title: 'Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: a83d0a11aacac3676aa78d9952f24f505949d24c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522558"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="575d7-102">Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="575d7-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="575d7-103">En el siguiente ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="575d7-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="575d7-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="575d7-104">Example</span></span>  
 <span data-ttu-id="575d7-105">En este código de ejemplo se usa `DllImport` para importar el punto de entrada del método `winmm.dll` de `PlaySound` como `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="575d7-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="575d7-106">El ejemplo tiene un formulario Windows Forms simple con un botón.</span><span class="sxs-lookup"><span data-stu-id="575d7-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="575d7-107">Al hacer clic en el botón, se abre un cuadro de diálogo <xref:System.Windows.Forms.OpenFileDialog> estándar de Windows para que pueda abrir un archivo y reproducirlo.</span><span class="sxs-lookup"><span data-stu-id="575d7-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="575d7-108">Cuando se selecciona un archivo de sonido, este se reproduce mediante el método `PlaySound()` de la biblioteca `winmm.dll`.</span><span class="sxs-lookup"><span data-stu-id="575d7-108">When a wave file is selected, it is played by using the `PlaySound()` method of the `winmm.dll` library.</span></span> <span data-ttu-id="575d7-109">Para obtener más información sobre este método, vea [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files) (Uso de la función PlaySound con archivos para forma de onda de sonido).</span><span class="sxs-lookup"><span data-stu-id="575d7-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="575d7-110">Busque y seleccione un archivo que tenga una extensión .wav y, después, haga clic en **Abrir** para reproducirlo mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="575d7-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="575d7-111">Un cuadro de texto muestra la ruta de acceso completa del archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="575d7-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="575d7-112">El cuadro de diálogo **Abrir archivos** se puede filtrar con los siguientes valores para que muestre solo los archivos que tengan la extensión .wav:</span><span class="sxs-lookup"><span data-stu-id="575d7-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="575d7-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="575d7-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="575d7-114">Para compilar el código</span><span class="sxs-lookup"><span data-stu-id="575d7-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="575d7-115">Cree un nuevo proyecto de aplicación para Windows C# en Visual Studio y asígnele el nombre **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="575d7-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="575d7-116">Copie el código anterior y péguelo sobre el contenido del archivo `Form1.cs`.</span><span class="sxs-lookup"><span data-stu-id="575d7-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="575d7-117">Copie el código siguiente y péguelo en el archivo `Form1.Designer.cs`, en el método `InitializeComponent()`, después de cualquier código existente.</span><span class="sxs-lookup"><span data-stu-id="575d7-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="575d7-118">Compile y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="575d7-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="575d7-119">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="575d7-119">.NET Framework Security</span></span>  
 <span data-ttu-id="575d7-120">Para obtener más información, vea [Seguridad en .NET](../../../standard/security/index.md).</span><span class="sxs-lookup"><span data-stu-id="575d7-120">For more information, see [Security in .NET](../../../standard/security/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575d7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="575d7-121">See Also</span></span>

- [<span data-ttu-id="575d7-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="575d7-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="575d7-123">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="575d7-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
- [<span data-ttu-id="575d7-124">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="575d7-124">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
- [<span data-ttu-id="575d7-125">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="575d7-125">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
