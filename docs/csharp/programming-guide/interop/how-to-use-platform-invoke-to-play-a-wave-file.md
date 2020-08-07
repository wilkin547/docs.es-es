---
title: 'Procedimiento Utilizar la invocación de plataforma para reproducir un archivo de sonido: Guía de programación de C#'
description: En el ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido WAV en el sistema operativo Windows.
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: b30cb08e2dcde0eb85e8d88a690ae24bf7ae7f22
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302989"
---
# <a name="how-to-use-platform-invoke-to-play-a-wav-file-c-programming-guide"></a><span data-ttu-id="3c2e5-103">Procedimiento Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3c2e5-103">How to use platform invoke to play a WAV file (C# Programming Guide)</span></span>

<span data-ttu-id="3c2e5-104">En el siguiente ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido WAV en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-104">The following C# code example illustrates how to use platform invoke services to play a WAV sound file on the Windows operating system.</span></span>

## <a name="example"></a><span data-ttu-id="3c2e5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c2e5-105">Example</span></span>

<span data-ttu-id="3c2e5-106">En este código de ejemplo se usa <xref:System.Runtime.InteropServices.DllImportAttribute> para importar el punto de entrada del método `winmm.dll` de `PlaySound` como `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-106">This example code uses <xref:System.Runtime.InteropServices.DllImportAttribute> to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="3c2e5-107">El ejemplo tiene un formulario Windows Forms simple con un botón.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-107">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="3c2e5-108">Al hacer clic en el botón, se abre un cuadro de diálogo <xref:System.Windows.Forms.OpenFileDialog> estándar de Windows para que pueda abrir un archivo y reproducirlo.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-108">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="3c2e5-109">Cuando se selecciona un archivo de sonido, se reproduce mediante el método `PlaySound()` de la biblioteca *winmm.dll*.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-109">When a wave file is selected, it is played by using the `PlaySound()` method of the *winmm.dll* library.</span></span> <span data-ttu-id="3c2e5-110">Para obtener más información sobre este método, vea [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files) (Uso de la función PlaySound con archivos para forma de onda de sonido).</span><span class="sxs-lookup"><span data-stu-id="3c2e5-110">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="3c2e5-111">Busque y seleccione un archivo que tenga una extensión .wav y, después, haga clic en **Abrir** para reproducirlo mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-111">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="3c2e5-112">Un cuadro de texto muestra la ruta de acceso completa del archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-112">A text box shows the full path of the file selected.</span></span>

<span data-ttu-id="3c2e5-113">El cuadro de diálogo **Abrir archivos** se puede filtrar con los siguientes valores para que muestre solo los archivos que tengan la extensión .wav:</span><span class="sxs-lookup"><span data-stu-id="3c2e5-113">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>

[!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]

[!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]

## <a name="compiling-the-code"></a><span data-ttu-id="3c2e5-114">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="3c2e5-114">Compiling the code</span></span>

1. <span data-ttu-id="3c2e5-115">Cree un proyecto de aplicación Windows Forms para C# en Visual Studio y asígnele el nombre **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-115">Create a new C# Windows Forms Application project in Visual Studio and name it **WinSound**.</span></span>

2. <span data-ttu-id="3c2e5-116">Copie el código anterior y péguelo sobre el contenido del archivo *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-116">Copy the code above, and paste it over the contents of the *Form1.cs* file.</span></span>

3. <span data-ttu-id="3c2e5-117">Copie el código siguiente y péguelo en el archivo *Form1.Designer.cs*, en el método `InitializeComponent()`, después de cualquier código existente.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-117">Copy the following code, and paste it in the *Form1.Designer.cs* file, in the `InitializeComponent()` method, after any existing code.</span></span>

     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]

4. <span data-ttu-id="3c2e5-118">Compile y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="3c2e5-118">Compile and run the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c2e5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c2e5-119">See also</span></span>

- [<span data-ttu-id="3c2e5-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3c2e5-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3c2e5-121">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="3c2e5-121">Interoperability Overview</span></span>](interoperability-overview.md)
- [<span data-ttu-id="3c2e5-122">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="3c2e5-122">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="3c2e5-123">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="3c2e5-123">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
