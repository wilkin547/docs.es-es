---
title: "Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2aacad0e8004e60471a59ebef695ddae5f7a2a7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="1f41e-102">Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1f41e-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="1f41e-103">En el siguiente ejemplo de código de C# se muestra cómo se usan los servicios de invocación de plataforma para reproducir un archivo de sonido en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="1f41e-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f41e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f41e-104">Example</span></span>  
 <span data-ttu-id="1f41e-105">En este código de ejemplo se usa `DllImport` para importar el punto de entrada del método `winmm.dll` de `PlaySound` como `Form1 PlaySound()`.</span><span class="sxs-lookup"><span data-stu-id="1f41e-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="1f41e-106">El ejemplo tiene un formulario Windows Forms simple con un botón.</span><span class="sxs-lookup"><span data-stu-id="1f41e-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="1f41e-107">Al hacer clic en el botón, se abre un cuadro de diálogo <xref:System.Windows.Forms.OpenFileDialog> estándar de Windows para que pueda abrir un archivo y reproducirlo.</span><span class="sxs-lookup"><span data-stu-id="1f41e-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="1f41e-108">Cuando se selecciona un archivo de sonido, este se reproduce mediante el método `PlaySound()` del método de ensamblado winmm.DLL.</span><span class="sxs-lookup"><span data-stu-id="1f41e-108">When a wave file is selected, it is played by using the `PlaySound()` method of the winmm.DLL assembly method.</span></span> <span data-ttu-id="1f41e-109">Para obtener más información sobre el método `PlaySound` de winmm.dll, vea [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553) (Usar la función PlaySound con archivos para forma de onda de sonido).</span><span class="sxs-lookup"><span data-stu-id="1f41e-109">For more information about winmm.dll's `PlaySound` method, see [Using the PlaySound function with Waveform-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).</span></span> <span data-ttu-id="1f41e-110">Busque y seleccione un archivo que tenga una extensión .wav y, después, haga clic en **Abrir** para reproducirlo mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="1f41e-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="1f41e-111">Un cuadro de texto muestra la ruta de acceso completa del archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1f41e-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="1f41e-112">El cuadro de diálogo **Abrir archivos** se puede filtrar con los siguientes valores para que muestre solo los archivos que tengan la extensión .wav:</span><span class="sxs-lookup"><span data-stu-id="1f41e-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1f41e-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1f41e-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="1f41e-114">Para compilar el código</span><span class="sxs-lookup"><span data-stu-id="1f41e-114">To compile the code</span></span>  
  
1.  <span data-ttu-id="1f41e-115">Cree un nuevo proyecto de aplicación para Windows C# en Visual Studio y asígnele el nombre **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="1f41e-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2.  <span data-ttu-id="1f41e-116">Copie el código anterior y péguelo sobre el contenido del archivo `Form1.cs`.</span><span class="sxs-lookup"><span data-stu-id="1f41e-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3.  <span data-ttu-id="1f41e-117">Copie el código siguiente y péguelo en el archivo `Form1.Designer.cs`, en el método `InitializeComponent()`, después de cualquier código existente.</span><span class="sxs-lookup"><span data-stu-id="1f41e-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  <span data-ttu-id="1f41e-118">Compile y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="1f41e-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1f41e-119">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1f41e-119">.NET Framework Security</span></span>  
 <span data-ttu-id="1f41e-120">Para obtener más información, vea [Seguridad de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=37122).</span><span class="sxs-lookup"><span data-stu-id="1f41e-120">For more information, see [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f41e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f41e-121">See Also</span></span>  
 [<span data-ttu-id="1f41e-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1f41e-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1f41e-123">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="1f41e-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="1f41e-124">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="1f41e-124">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 [<span data-ttu-id="1f41e-125">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="1f41e-125">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="1f41e-126">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="1f41e-126">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
